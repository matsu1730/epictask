# epictask - Deploy ACI utilizando imagem no ACR

Segue abaixo DDL das tables

```
Hibernate: 
    
    create table tb_role (
       id bigint identity not null,
        name varchar(255),
        primary key (id)
    )
Hibernate: 
    
    create table tb_task (
       id bigint identity not null,
        description varchar(255),
        score int not null check (score>=1),
        status int not null check (status<=100 AND status>=0),
        title varchar(255),
        primary key (id)
    )
Hibernate: 
    
    create table tb_user (
       id bigint identity not null,
        email varchar(255),
        name varchar(255),
        password varchar(255),
        primary key (id)
    )
Hibernate: 
    
    create table tb_user_roles (
       user_id bigint not null,
        roles_id bigint not null
    )
Hibernate: 
    
    alter table tb_user_roles 
       add constraint FK1vtq78sjf399g49sd0voq05c0 
       foreign key (roles_id) 
       references tb_role
Hibernate: 
    
    alter table tb_user_roles 
       add constraint FK19t64ocsol5x06fy2cytp7gey 
       foreign key (user_id) 
       references tb_user
```
