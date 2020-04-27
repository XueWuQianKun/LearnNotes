### MyBatis

> ##### 映射map，下划线转驼峰，大写变小写

>   1、自定义  ***MapWrapper***
>
> ````java
> public class CustomMapWrapper extends MapWrapper {
>     public CustomMapWrapper(MetaObject metaObject, Map<String, Object> map) {
>         super(metaObject, map);
>     }
> 
>     @Override
>     public String findProperty(String name, boolean useCamelCaseMapping) {
>         if (useCamelCaseMapping){
>             return CaseFormat.UPPER_UNDERSCORE.to(CaseFormat.LOWER_CAMEL,name);
>         }
>         return name;
>     }
> }
> ````
>
> 2、自定义  ***MapWrapperFactory***
>
>  ````java
> public class CustomMapWrapperFactory implements ObjectWrapperFactory {
> 
>     @Override
>     public boolean hasWrapperFor(Object o) {
>         return o != null && o instanceof Map;
>     }
> 
>     @Override
>     public ObjectWrapper getWrapperFor(MetaObject metaObject, Object o) {
>         return new CustomMapWrapper(metaObject,(Map)o);
>     }
> }
>  ````
>
> 3、在配置类中注入自定义的  ***MapWrapperFactory***
>
> ````java
>     @Bean
>     public SqlSessionFactory sqlSessionFactory(DataSource dataSource) throws Exception
>     { 
>       	// 其他配置...略
>      		SqlSessionFactoryBean sessionFactory = new SqlSessionFactoryBean();
>       	// 其他配置....略
>         sessionFactory.setObjectWrapperFactory(new CustomMapWrapperFactory());
>         return sessionFactory.getObject();
>     }
> ````
>
> 4、需设置（由于***CustomerWrapper***中是根据这个来控制是否使用自定义map转换的）
>
> ````xml
> mybatis.configuration.map-underscore-to-camel-case=true
> ````
>
> 