关于odoo-dock
======

使用docker搭建odoo的开发环境，系统为debian:stretch，odoo版本默认为11.0，对于不同版本可以在.env配置ODOO_VERSION，数据库使用postgresql:9.4

### odoo docker开发环境搭建
======

- 拉取代码库
- 配置 .env文件
> ```
> ODOO_VERSION=11.0
>
> POSTGRESQL_TAG=9.4
> POSTGRESQL_USER=odoo
> POSTGRES_PASSWORD=odoo
> POSTGRES_EXPODE_PORT=5432
>
> NETWORKS_DRIVER=bridge
>
> VOLUMES_DRIVER=local
>
> APP_CODE_PATH_HOST=/home/chan/code/odoo-11.0
> APP_CODE_PATH_CONTAINER=/code/odoo-11.0
> ODOO_APP_PORT=8099
> ```

- 执行`docker-compose build odoo`，编译odoo镜像
- 执行 `docker-compose up odoo`，创建container并启动,后续要启动container的只需要执行`docker-compose start odoo`,如果需要清除此compose的container/network/volume等相关文件，执行`docker-compose down`

