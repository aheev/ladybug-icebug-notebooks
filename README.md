# Ladybug + Icebug Notebooks

This workspace contains a reproducible `uv` project and notebook demos for the
Ladybug Arrow query path feeding Icebug graph analytics.

## Notebook Index

Notebooks are listed from simpler graph-query examples to more advanced storage
and analytics workflows.

1. [Python Tutorial: Analyze a Social Network](ladybug-python-social-network.ipynb) -
   introductory Ladybug graph querying from Python.
2. [Ladybug: query a Star Wars graph stored in DuckDB](ladybug_duckdb_attached_starwars.ipynb) -
   attach a DuckDB database and declare a relationship table backed by an
   attached DuckDB table.
3. [Ladybug nightly + Icebug: Star Wars graph analytics](ladybug_icebug_starwars.ipynb) -
   query Arrow-backed Star Wars data, persist it to native Ladybug storage,
   export CSR, and run Icebug analytics.
4. [Ladybug nightly + Icebug: Star Wars graph analytics with Arrow CSR](ladybug_icebug_memory_starwars.ipynb) -
   build Arrow CSR tables in memory and share them between Ladybug and Icebug.
5. [Ladybug Icebug Community Detection](ladybug_icebug_comm_detection.ipynb) -
   export an in-memory Ladybug graph to Parquet, import it into a fresh
   instance, run Icebug Leiden, and write communities back to the nodes.
6. [Ladybug nightly + Icebug: Karate Club graph analytics from icebug-disk](ladybug_icebug_disk_karate.ipynb) -
   convert DuckDB tables to icebug-disk Parquet, load them natively in Ladybug,
   and run Icebug algorithms.
7. [pgembed: embedded Postgres logical replication](pgembed_logical_replication.ipynb) -
   start two embedded Postgres clusters with pgembed over Unix domain sockets,
   publish logical WAL changes from the primary, and read replicated rows from
   the secondary.

Open the notebook index directly with:

```bash
uv run jupyter notebook index.ipynb
```

Or open an individual notebook with:

```bash
uv run jupyter notebook <notebook>.ipynb
```

Or execute one from the CLI:

```bash
uv run jupyter nbconvert --to notebook --execute ladybug_icebug_starwars.ipynb --inplace
```

The pgembed replication notebook uses an optional dependency group:

```bash
uv sync --extra postgres
```
