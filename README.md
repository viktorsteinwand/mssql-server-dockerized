# MS-SQL Server in Docker

Demo for having Microsoft SQL Server installed in docker (linux container).

## Prerequisites

- Latest docker engine installed
- Latest docker-compose installed

Tested on Docker for Mac (**docker 18.06.0-ce** and **docker-composer 1.22.0**)  

## How to start

Prepare env file:

```sh
cp .env.example .env
```

Replace the demo password with yours. Then start the SQL Server:

```sh
docker-composer up -d
bin/provision-database -p <Your-SA-Password>
```

## Demo

![Demo](./demo.gif)

## Usage

### CLI

Commands can be executed direct on the CLI by using the following command:

```sh
bin/sqlcmd -S mssql -U SA -P <YOUR-SA-PASSWORD> -d Names -I -Q "SELECT TOP(5) * FROM Names;"
```

### SQL Operations Studio

Connect to the database hosted on localhost via [SQL Operations Studio](https://docs.microsoft.com/en-us/sql/sql-operations-studio/download?view=sql-server-2017) and browse to the `Names` table.

---

## Links

- This demo is basically based on idea from [Shayne Boyer](https://github.com/spboyer): [https://github.com/spboyer/docker-why](https://github.com/spboyer/docker-why)
- [Scott Hanselman - SQL Server on Linux or in Docker plus cross-platform SQL Operations Studio](https://www.hanselman.com/blog/SQLServerOnLinuxOrInDockerPlusCrossplatformSQLOperationsStudio.aspx)
