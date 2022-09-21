# GuestBookMyBatis


create table gntp.guestbook
(
    seq        INT(10) auto_increment
        primary key,
    user_id    VARCHAR(10)                            not null,
    title      VARCHAR(50)                            not null,
    content    VARCHAR(200)                           not null,
    reg_date   DATETIME(19) default CURRENT_TIMESTAMP not null,
    read_count INT(10)      default 0                 not null
);

create table gntp.reply
(
    reply_seq INT(10) auto_increment
        primary key,
    content   VARCHAR(100)                           not null,
    reg_date  DATETIME(19) default CURRENT_TIMESTAMP not null,
    seq       INT(10)                                not null,
    constraint reply_ibfk_1
        foreign key (seq) references gntp.guestbook (seq)
);
