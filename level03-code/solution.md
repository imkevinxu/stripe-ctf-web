[Stripe CTF Level 3](https://level03-2.stripe-ctf.com/user-lzssucmeeo/)
--------------------

Password
--------
vUMuuSTRNO

Solution
--------
SQL injection to return a specific query. Combined an empty query UNION with a literal query that has the user id and a known hash for a known password and blank salt.

Found the sha256 hash for " " from this [generator](http://www.everpassword.com/sha-256-generator) which produced the hash 36a9e7f1c95b82ffb99743e0c5c4ce95d83c9a430aac59f84ef3cbfab6145068

Then created this sql so I could input the password " " to match the hash

    ' UNION SELECT '1' AS 'id', '36a9e7f1c95b82ffb99743e0c5c4ce95d83c9a430aac59f84ef3cbfab6145068' AS 'password_hash', '' AS 'salt

Knowledge
---------

    SQL Union
    Literal SQL queries
    sha256 hashing