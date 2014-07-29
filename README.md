NuoDB-migrator
==============

A generic script that will run the NuoDB migration tool. Has both a linux/macosx and a windows version

This zip archive contains four files:

  mac/linux version of this migrate script:
    migrate.sh - the shell script
    migrate.env - the environment variables to be defined for the script

  windows version of this migrate script:
    migrate.bat - the windows dos script
    migrate_win.env - the environment variables to be defined for the script

The purpose of the env file:
  define the environment variables that need to be set for the script to run.
  defines variables related to:
    location of the migrator tool
    location of the output files from the migrator tool (dump directory)
    source database
    target database

Once you have defined your environment variables, run the script for your environment, passing one of the following parameters:

  most common:
    do_all              generate tables and indexes, then load data (small databases)
    do_all_in_steps     generate tables, load data, then create indexes (large databases)

  other options:
    dump_data_only      dump the table data only
    dump_data_indexes   dump the table data and indexes
    load_only           load what was dumped, data only, or data and indexes
    dump_load_indexes   create indexes only. no data.
    ddl_only            generate schema ddl script only

additional options can be added to the DUMP, LOAD, or SCHEMA commands in these scripts. These options are documented here:
  http://doc.nuodb.com/display/doc/NuoDB+Migrator

