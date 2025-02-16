# Telemetry and version checking
Timescale collects anonymous usage data to help us better understand and assist
our users. It also helps us provide some services, such as automated version
checking. Your privacy is the most important thing to us, so we do not collect
any personally-identifying information. In particular, the `UUID` (user ID)
fields contain no identifying information, but are randomly generated by
appropriately seeded random number generators.

This is an example of the JSON data file that is sent to our servers about a
specific deployment:

```javascript
{
	"db_uuid": "26917841-2fc0-48fd-b096-ba19b3fda98f",
	"license": {
		"edition": "community"
	},
	"exported_db_uuid": "8dd4543c-f44e-43c9-a666-02d23bb09b90",
	"installed_time": "2000-04-17 10:56:59.427738-04",
	"last_tuned_time": "2001-02-03T04:05:06-0300",
	"last_tuned_version": "1.0.0",
	"install_method": "source",
	"os_name": "Linux",
	"os_release": "4.9.125-linuxkit",
	"os_version": "#1 SMP Fri Sep 7 08:20:28 UTC 2018",
	"os_name_pretty": "Debian GNU/Linux 8 (jessie)",
	"postgresql_version": "12.4",
	"timescaledb_version": "1.7.0",
	"build_architecture": "x86_64",
	"build_architecture_bit_size": "64",
	"build_os_name": "Linux",
	"build_os_version": "4.9.125-linuxkit",
	"data_volume": "65982148",
	"db_metadata":{
			"promscale_version": "0.1.0",
			"promscale_commit_hash": ""
    },
	"num_hypertables": "3",
	"num_continuous_aggs": "0",
	"num_reorder_policies": "1",
	"num_drop_chunks_policies": "2",
	"related_extensions":{
			"pg_prometheus": "false",
			"PostGIS": "true",
			"promscale": "true"
    }
}
```

If you want to see the exact JSON data file that is being sent to our servers,
you can use the [`get_telemetry_report`][get_telemetry_report] API call.

<highlight type="note">
Telemetry reports are different if you are using an open source or community
version of TimescaleDB. For these versions, the report includes an `edition`
field, with a value of either `apache_only` or `community`.
</highlight>

## Change what is included the telemetry report
If you want to adjust which metadata is included or excluded from the telemetry
report, you can do so in the `_timescaledb_catalog.metadata` table. Metadata
which has `include_in_telemetry` set to `true`, and a value of
`timescaledb_telemetry.cloud`, is included in the telemetry report.

## Version checking
Telemetry reports are sent periodically in the background. In response to the
telemetry report, the database receives the most recent version of TimescaleDB
available for installation. This version is recorded in your server logs, along
with any applicable out-of-date version warnings. You do not have to update
immediately to the newest release, but we highly recommend that you do so, to
take advantage of performance improvements and bug fixes.

## Disable telemetry
We highly recommend that you leave telemetry enabled, as it helps us to keep
improving, and it provides useful functionality for you. However, you can
disable telemetry if you need to for any reason. You can disable telemetry for a
specific database, or for an entire instance.

<highlight type="important">
If you disable telemetry, the version checking functionality is also disabled.
</highlight>

<procedure>

### Disabling telemetry
1.  Open your PostgreSQL configuration file, and locate
		the `timescaledb.telemetry_level` parameter. See our
		[PostgreSQL configuration file][postgres-config] instructions for locating
		and opening the file.
1. 	Change the parameter setting to `off`:
		```txt
	  timescaledb.telemetry_level=off
	 	```
1. 	Reload the configuration file:
		```bash
		pg_ctl
		```
1. 	Alternatively, you can use this command at the `psql` prompt, as the root
		user:
	  ```sql
		ALTER [SYSTEM | DATABASE | USER] { *db_name* | *role_specification* } SET timescaledb.telemetry_level=off
	  ```
	 	This command disables telemetry for the specified system, database, or user.

</procedure>

<procedure>

### Enabling telemetry
1. 	Open your PostgreSQL configuration file, and locate
		the `timescaledb.telemetry_level` parameter. See our
		[PostgreSQL configuration file][postgres-config] instructions for locating
		and opening the file.
1. 	Change the parameter setting to `off`:
		```txt
		timescaledb.telemetry_level=basic
		```
1. 	Reload the configuration file:
		```bash
		pg_ctl
		```
1. 	Alternatively, you can use this command at the `psql` prompt, as the root
		user:
		```sql
		ALTER [SYSTEM | DATABASE | USER] { *db_name* | *role_specification* } SET timescaledb.telemetry_level=basic
		```
		This command enables telemetry for the specified system, database, or user.

</procedure>

[get_telemetry_report]: /api/:currentVersion:/administration/get_telemetry_report
[postgres-config]: /how-to-guides/configuration/postgres-config
