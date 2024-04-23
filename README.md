# [SQLFluff](https://docs.sqlfluff.com/en/stable/index.html)

<img src='https://docs.sqlfluff.com/en/stable/_static/images/sqlfluff-lrg.png' width='20%' height='20%'>

Using **SQLFluff** to lint and format SQL codes.

![image](https://github.com/Saphall/SQLFluff/assets/66344649/3365146c-a915-4893-9a1c-3b93d5e6b9a9)

Examples:

```zsh
sqlfluff lint --dialect postgres .
sqlfluff fix --dialect tsql src/test.sql
```

> Further: [CLI Reference](https://docs.sqlfluff.com/en/stable/cli.html#cli-reference)

## [Configuration](https://docs.sqlfluff.com/en/stable/configuration.html#config)

SQLFluff accepts configuration either through the command line or through configuration files. For file based configuration SQLFluff will look for the following files in order. Later files will (if found) will be used to overwrite any values read from earlier files.

* `setup.cfg`
* `tox.ini`
* `pep8.ini`
* `.sqlfluff`
* `pyproject.toml`

## Installation and Use

### 1. Install sqlfluff

```zsh
pip install sqlfluff
```

### 2. Add config file like [.sqlfluff](./.sqlfluff)

### 3. Test the linting

```powershell
sqlfluff lint **/*.sql
```

<details>
<summary>Example SQL Code:</summary>
<br>
<code>select id, name from test;
</code>
<br>
<img src='https://github.com/Saphall/SQLFluff/assets/66344649/4c958aa2-5e95-4f0d-b352-9cec615c042d'>
</details>

### 4. Fix the SQL Code

```powershell
sqlfluff fix **/*.sql
```

<details>
<summary>Fixed SQL Code:</summary>
<br>
<code>SELECT
  id,
  name
FROM test;
</code>
<br>
<img src='https://github.com/Saphall/SQLFluff/assets/66344649/b6436dc2-8887-4d86-b711-9b91348f71dd'>
</details>

## Workflow

On the basis of [Rolling out SQLFluff with a new team](https://docs.sqlfluff.com/en/stable/teamrollout.html), added the workflow test.

We check the SQL lint using the workflow file: [sql_lint.yml](.github/workflows/sql_lint.yml)

> Refer: [PR](https://github.com/Saphall/SQLFluff/pull/1)

<details>
<summary>Failed CI</summary>
<br>
<img src= ''>
</details>

<details>
<summary>Passed CI</summary>
<br>
<img src= ''>
</details>
