# spring_boot_auth_jdbc

------ Create following table before running the application

create table users (
    username varchar(50) not null primary key,
    password varchar(120) not null,
    enabled boolean not null
);

create table authorities (
    username varchar(50) not null,
    authority varchar(50) not null,
    foreign key (username) references users (username)
);

----- Insert following data into the table


INSERT INTO `users`  (`username`,`password`,  `enabled`) 
VALUES 
('john',' $2a$12$V9IuZkwkv0cdiIpGh9dZAO9HG0z9FhFCpyuBYb/eYlqNwtGoey3JG',1),
('mary',' $2a$12$V9IuZkwkv0cdiIpGh9dZAO9HG0z9FhFCpyuBYb/eYlqNwtGoey3JG',1),
('susan',' $2a$12$V9IuZkwkv0cdiIpGh9dZAO9HG0z9FhFCpyuBYb/eYlqNwtGoey3JG',1);

INSERT INTO `authorities` (`username`,`authority`)
VALUES 
('john','ROLE_GUEST'),
('mary','ROLE_GUEST'),
('susan','ROLE_GUEST'),
('john','ROLE_ADMIN');
