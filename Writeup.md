### bandit0
`bandit0`
* `cat readme`

### bandit1
`ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`
* file starting with - are opened differently Linux assumes - to be options of a command
* `cat < -`

### bandit2
`263JGJPfgU6LtdEvgfWU1XP5yac29mFx`
* escape using \
* and also `cat < --`

### bandit3
`MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`
* `ls -a` to see everything

### bandit4
`2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`
* `for i in ./* ; do cat $i ;printf '\n' ;done`
* `cat ./* | strings`

### bandit5
`4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`
* `(for i in ./*/{*,.[!.]*} ; do wc -c "$i" ;done; ) | grep 1033`
* `{*,.[!.]*}` * means anything, `.[!.]*` means starting with a . but 2nd char (has to be there) should not be a dot and then anything

### bandit6
`HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`
* `find ../.. bandit7 |grep bandit7`

### bandit7
`morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj`
* `grep millionth data.txt`

### bandit8
`dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`
* uniq is about constitutive lines uniqueness
* `sort data.txt | uniq -c`

### bandit9
`4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`
* `strings data.txt`

### bandit10
`FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`
* 64 bit encoding
* `base64 -d data.txt`

### bandit11
`dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`
* vigenere cipher knowing the plaintext "The password is"

### bandit12
`7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4`
* lot of decompression 
* `xxd -r` reberse (dump - data) 
* `-d` decompress
* `-xO` extract and output to stdout
* `xxd -r data.txt | gzip -d | bzip2 -d | gzip -d |tar -xO |tar -xO |bzip2 -d | tar -xO | gzip -d`

### bandit13
`FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn`
* `scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private fil`
* scp copies from secure shells its ssh derivative.copy sshkey.private on the local machile in the file name 'fil'
* note: P is capital in -P
* `chmod 700 fil`
* `ssh -i fil bandit14@bandit.labs.overthewire.org -p 2220`

### bandit14
`MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS`
* `cat ../../etc/bandit_pass/bandit14`
* `nc localhost 30000`

### bandit15
`8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo`
* `openssl s_client localhost:30001`

### bandit16
`kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx`
* `openssl s_client  -quiet localhost:31790`
* -quiet because Keyupdate was annoing so removed outputs using quiet
* then i got the private key the `$ ssh -i`

### bandit17
`EReVavePLFHtFlFsjn3hyzMlvSuSAcRD`
* `diff passwords.new passwords.old`

### bandit18
`x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO`
* remotely execute command
* `ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme`

### bandit19
`cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8`
* i can run command as bandit 20
* `./bandit20-do cat ../../etc/bandit_pass/*`

### bandit20
`0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO`
* `echo pass | nc -l -p 1233 &`
* netcat listen to connection on port 1233 (randomly chosen number)
* & in the background and echo pass
* in foreground `./suconnect 1233` 
* suconnect if recives correct pass that it does as i have echoed that then it shows the next pass

### bandit21
`EeoULMCra2q0dSkYj561DX7s1CpBuOBt`
* `/etc/cron.d/cronjob_bandit22 ----> ../../usr/bin/cronjob_bandit22.sh ----> tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv -->tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q`

### bandit22
`tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q`
* just do that is done in that file  md5

### bandit23
`0Zf11ioIjMVN551jX3CmStKLYqjk54Ga`
* that file is called on bandit24 system every once in a while (this execution is not in foreground ,not even in front of me)
* whenever that happens i will store pass in a temp file 
* then i will se the contents of that file bingo!! (dont forget to make permissions to 777)

### bandit24
`gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8`
* `python3 -c "print('\n'.join(['gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 '+str(i) for i in range(1000,10000)]))" | nc localhost 30002`

### bandit25
`iCi86ttT4KSNe1armKiwbQNmB3YJP3q4`
* to see which shell is used 
* `cat /etc/passwd` 
* shell is `/usr/bin/showtext`
* `cat /usr/bin/showtext` 
* more is used here and then exit means when we try to do this 
* `scp -P 2220 bandit26@bandit.labs.overthewire.org:sshkey.private fil`
* `chmod 700 fil` 
* `ssh -p 2220 bandit26@bandit.labs.overthewire.org -i fil`
* it exits automatically..
* more command just prints things but if the things dont fit screen we get more.. and paused 
* when we are in more type 'v' will open in vim
* vim have command :e to open a file 
* `:e /etc/bandit_pass/bandit26`

### bandit26
`s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ`