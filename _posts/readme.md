-----------------
The Answers to Instaclustr Technical Test - Graduates
-- By Fei Wang (jevy.wangfei@gmail.com)

Work Log:


-----------------
## 1. Bash Scripting
* `./1_recursive_files_words_counter.sh` to view result.
* `./1_letters_frequency_hist.sh` to display hist.

## 2. General Administration
* `./1_letters_frequency_hist.sh` to check result.

## 3. General Programming
* `javac GeneralProgramming.java` to compile.
*  `java -cp . GeneralProgramming` to run it.

## 4. Concurrency Programming


## 5. SQL Programming
Using the included database schema file ( *interviewSchema.psql* )1 , for each question write an SQL query that produces the answers.
1. List the title, release year, genre and director of all  **'action'**  movies.
```sql
SELECT m.title, m.release_year, m.genre, m.director FROM movies m
where m.genre="action";
```
2. List the actors and their birth year for all movies directed by  **'Wes Anderson'** .
```sql
SELECT a.name, a.birth_year FROM actors a inner join  movie_cast c inner join movies m  
on a.name=c.actor and a.birth_year = c.birth_year and c.movie = m.title and c.movie_release_year = m.release_year and m.director = "Wes Anderson";
```

```sql
SELECT c.actor, c.birth_year FROM  movie_cast c inner join movies m  
on c.movie = m.title and c.movie_release_year = m.release_year and m.director = "Wes Anderson";
```
3. List the title, release year, genre and director of all movies staring  **'Jeff Goldblum'** but not  **'Bruce Willis'** .
```sql
select m.title, m.release_year, m.genre, m.director from movies m inner join (
        select a.movie as title, a.movie_release_year as release_year from movie_cast a
        where a.actor = "Jeff Goldblum" and not exists (
              select * from movie_cast b
              where a.movie=b.movie and a.movie_release_year=b.movie_release_year and b.actor = "Bruce Willis")
        ) s
where m.title=s.title and m.release_year = s.release_year;
```

## 6. Using Cassandra
* Create Instaclustr account and wait until Instaclustr finishing Cassandra joining.
* Download Cassandra v3.10, unpress it and `cd` to `apache-cassandra/bin` directory in terminal.
* Using connection information provided on `interviewTest (Cluster Dashboard)/Connection Info` and `https://support.instaclustr.com/hc/en-us/articles/216238308` to connect Cassandra:
```bash
./cqlsh 52.24.8.111  9042 –u iccassandra -p b13e656dbbd8762b645e314914a4165f
``` .

* Create keyspace:
```sql
create keyspace `moviecategory` with replication = {'class':'SimpleStrategy','replication_factor':3};
```

* Create table:
```sql
use moviecategory;

CREATE TABLE movies (
	title text,
	release_year int,
	genre text,
	director text,
	PRIMARY KEY (title, release_year)
);
```

* Load data:
```sql
COPY movies FROM ('instaclustr/movies.csv') WITH DELIMITER=',' AND HEADER='true';
```


## 7. Cloud Computing Theory
### 7.1 What is the difference between container based virtualization and hypervisor based virtualization?
**Answer:** The difference between Container based virtualization (using `C` in short) and Hypervisor based virtualization (using `H` in short) are listed as following:
 - Different virtual ideas: `H` 'creates' virtual hardwares on host OS, and the virtual machines just like physical computer. but  `C`'s virtualization is done at host OS level instead of at hardware level.
 - Resource sharing: `H` doesn't share any computing resources with other. But `C` shares host's kernel with other `C`s.
 - Performance: With the increase of more `H`s on host server, the performance of each `H` will be impacted greatly.  However, because of sharing resources, `C`s can automatically allocate resources to busier `C`s.


### 7.2 In Amazon Web Services, explain the difference between a Region, Availability Zone and Instance in relation to fault domains.
**Answer:** Services provided by Amazon are hosted world-widely. A physical place where hosts Amazon services is called `Region`. In each `Region`, there are multiple, isolated locations called `Availability Zones`. An instance runs in specific `Availability Zones`.
Ref. http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html


## 8. Networking Theory
1. The subnet should be 255.252.0.0, or /14 in CIDR.
2. NAT (Natwork Address Translation): Map internal private addresses and their port to public addresses (public addresses come from a public address pool) with their ports not changed.
   PAT (Port Address Translation): Map internal private addresses and their ports to a public address with different ports.  
3. VPN (Virtual Private Network): VPN is a technology which creates a security private connection over a public  network. Besides security, VPN also allow people remotely access resources available within a private network.

## 9. Memory Management
