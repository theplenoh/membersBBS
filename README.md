# membersBBS

Members-only BBS for practice

## MySQL Table Statements
### Table `mbbs_users`
```
CREATE TABLE mbbs_users (
    user_id int(11) NOT NULL AUTO_INCREMENT, 
    username varchar(15) NOT NULL UNIQUE, 
    user_group bit NOT NULL '0', 
    password varchar(255) NOT NULL, 
    nickname varchar(45) NOT NULL, 
    email char(80), 
    PRIMARY KEY(user_id)
) ENGINE=MyISAM DEFAULT CHARSET=utf8;
```
### Table `mbbs_board`
```
CREATE TABLE mbbs_board (
    post_id int(11) NOT NULL AUTO_INCREMENT, 
    user_id int(11) NOT NULL, 
    title varchar(70) NOT NULL, 
    content text NOT NULL, 
    datetime int(11) NOT NULL, 
    ip_addr varchar(16) NOT NULL, 
    views int(11) NOT NULL default '0', 
    PRIMARY KEY(post_id), 
    FOREIGN KEY(user_id) REFERENCES mbbs_users(user_id) ON UPDATE CASCADE
) ENGINE=MyISAM DEFAULT CHARSET=utf8;
```

## License Info
This repository is released under GPL v2.
