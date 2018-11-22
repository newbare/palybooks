# palybooks
## Este exemplo possui uma configuração em cluster com dois Nós;
## Possui exemplo de como configurar os pontos senssíveis;
## Configurações de banco de dados:
WSO2_USER_DB --> deve possuir grant all sobre todos os demais schemas

WSO2_USER_DB = db_wso2_user_schema
REGISTRY_DB = db_wso2_registry_schema
REGISTRY_LOCAL1 = db_wso2_registry_local1_schema

 priv: '{{ db_wso2_user_schema }}.*:ALL,GRANT/{{ db_wso2_registry_schema }}.*:ALL,GRANT/{{ db_wso2_registry_local1_schema }}.*:ALL,GRANT'
 
 ## O script de carga devera ser o mesmo para todos:
 wso2ei_script: <wso2ei_home>/dbscripts/mysql.sql
 WSO2_USER_DB = wso2ei_script
 REGISTRY_DB = wso2ei_script
 REGISTRY_LOCAL1 = wso2ei_script
