---
Title: Redis Enterprise Software release notes 7.4.6
alwaysopen: false
categories:
- docs
- operate
- rs
compatibleOSSVersion: Redis 7.2.4
description: Support for SHA-384 certificates in client authentication. rlcheck output in support packages. New parameters for optimize_shard_placement and recover database REST API requests.
hideListLinks: true
linkTitle: 7.4.6 releases
toc: 'true'
weight: 69
---

​[​Redis Enterprise Software version 7.4.6](https://redis.com/redis-enterprise-software/download-center/software/) is now available!

## Highlights

This version offers:
 
- Support for SHA-384 certificates in client authentication

- `rlcheck` output in support packages

- New parameters for `optimize_shard_placement` and `recover` database REST API requests

## Detailed release notes

For more detailed release notes, select a build version from the following table:

{{<table-children columnNames="Version&nbsp;(Release&nbsp;date)&nbsp;,Major changes,OSS&nbsp;Redis compatibility" columnSources="LinkTitle,Description,compatibleOSSVersion" enableLinks="LinkTitle">}}

## Version changes

### Product lifecycle updates

#### End-of-life policy extension

The end-of-life policy for Redis Enterprise Software versions 6.2 and later has been extended to 24 months after the formal release of the subsequent major version. For the updated end-of-life schedule, see the [Redis Enterprise Software product lifecycle]({{<relref "/operate/rs/installing-upgrading/product-lifecycle">}}).

#### Supported upgrade paths

After August 31, 2024, Redis Enterprise Software versions 6.2.4 and 6.2.8 will not be included in [supported upgrade paths]({{<relref "/operate/rs/installing-upgrading/upgrading/upgrade-cluster#supported-upgrade-paths">}}) for Redis Enterprise Software versions beyond 7.4.x. Redis Enterprise Software versions 6.2.10, 6.2.12, and 6.2.18 will continue to be part of the upgrade path.

The next major Redis Enterprise Software release will still bundle Redis database version 6.2 and allow database upgrades from Redis database version 6.2 to 7.x.

See the [Redis Enterprise Software product lifecycle]({{<relref "/operate/rs/installing-upgrading/product-lifecycle">}}) for more information about release numbers.

### Deprecations

#### Legacy UI deprecation

The legacy UI is deprecated in favor of the new Cluster Manager UI and will be removed in a future release.

#### Redis 6.0 database deprecation

Redis database version 6.0 is deprecated as of Redis Enterprise Software version 7.4.2 and will be removed in a future release.

To prepare for the future removal of Redis 6.0:

- For Redis Enterprise 6.2.* clusters, upgrade Redis 6.0 databases to Redis 6.2. See the [Redis 6.2 release notes](https://raw.githubusercontent.com/redis/redis/6.2/00-RELEASENOTES) for the list of changes.

- For Redis Enterprise 7.2.4, 7.4.2, and 7.4.6 clusters, upgrade Redis 6.0 databases to Redis 7.2. Before you upgrade your databases, see the list of [Redis 7.2 breaking changes]({{< relref "/operate/rs/release-notes/rs-7-2-4-releases/rs-7-2-4-52#redis-72-breaking-changes" >}}) and update any applications that connect to your database to handle these changes.

### Upcoming changes

#### Default image change for Redis Enterprise Software containers

Starting with version 7.6, Redis Enterprise Software containers with the image tag `x.y.z-build` will be based on RHEL instead of Ubuntu.

This change will only affect you if you use containers outside the official [Redis Enterprise for Kubernetes]({{<relref "/operate/kubernetes">}}) product and use Ubuntu-specific commands.

To use Ubuntu-based images after this change, you can specify the operating system suffix in the image tag. For example, use the image tag `7.4.2-216.focal` instead of `7.4.2-216`.

### Supported platforms

The following table provides a snapshot of supported platforms as of this Redis Enterprise Software release. See the [supported platforms reference]({{< relref "/operate/rs/references/supported-platforms" >}}) for more details about operating system compatibility.

<span title="Check mark icon">&#x2705;</span> Supported – The platform is supported for this version of Redis Enterprise Software and Redis Stack modules.

<span title="Warning icon">&#x26A0;&#xFE0F;</span> Deprecation warning – The platform is still supported for this version of Redis Enterprise Software, but support will be removed in a future release.

| Redis Enterprise<br />major versions | 7.4 | 7.2 | 6.4 | 6.2 |
|---------------------------------|:-----:|:-----:|:-----:|:-----:|
| **Release date** | Feb 2024 | Aug 2023 | Feb 2023 | Aug 2021 |
| [**End-of-life date**]({{< relref "/operate/rs/installing-upgrading/product-lifecycle#endoflife-schedule" >}}) | Determined after<br />next major release | July 2025 | Feb 2025 | Aug 2024 |
| **Platforms** | | | | |
| RHEL 9 &<br />compatible distros<sup>[1](#table-note-1)</sup> | <span title="Supported">&#x2705;</span> | – | – | – |
| RHEL 8 &<br />compatible distros<sup>[1](#table-note-1)</sup> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> |
| RHEL 7 &<br />compatible distros<sup>[1](#table-note-1)</sup> | – | <span title="Deprecated">&#x26A0;&#xFE0F;</span> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> |
| Ubuntu 20.04<sup>[2](#table-note-2)</sup> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> | – |
| Ubuntu 18.04<sup>[2](#table-note-2)</sup> | <span title="Deprecated">&#x26A0;&#xFE0F;</span> | <span title="Deprecated">&#x26A0;&#xFE0F;</span> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> |
| Ubuntu 16.04<sup>[2](#table-note-2)</sup> | – | <span title="Deprecated">&#x26A0;&#xFE0F;</span> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> |
| Amazon Linux 2 | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> | – |
| Amazon Linux 1 | – | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> |
| Kubernetes<sup>[3](#table-note-3)</sup> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> |
| Docker<sup>[4](#table-note-4)</sup> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> | <span title="Supported">&#x2705;</span> |

1. <a name="table-note-1" style="display: block; height: 80px; margin-top: -80px;"></a>The RHEL-compatible distributions CentOS, CentOS Stream, Alma, and Rocky are supported if they have full RHEL compatibility. Oracle Linux running the Red Hat Compatible Kernel (RHCK) is supported, but the Unbreakable Enterprise Kernel (UEK) is not supported.

2. <a name="table-note-2" style="display: block; height: 80px; margin-top: -80px;"></a>The server version of Ubuntu is recommended for production installations. The desktop version is only recommended for development deployments.

3. <a name="table-note-3" style="display: block; height: 80px; margin-top: -80px;"></a>See the [Redis Enterprise for Kubernetes documentation]({{< relref "/operate/kubernetes/reference/supported_k8s_distributions" >}}) for details about support per version and Kubernetes distribution.

4. <a name="table-note-4" style="display: block; height: 80px; margin-top: -80px;"></a>
[Docker images]({{< relref "/operate/rs/installing-upgrading/quickstarts/docker-quickstart" >}}) of Redis Enterprise Software are certified for development and testing only.

## Known issues

- RS61676: Full chain certificate update fails if any certificate in the chain does not have a Common Name (CN).

- RS119958: The `debuginfo` script fails with the error `/bin/tar: Argument list too long` if there are too many RocksDB log files.

- RS122570: REST API `POST /crdbs` responds with a confusing error message if the cluster does not have the requested CRDB-compatible module that complies with the requested featureset.

## Known limitations

#### New Cluster Manager UI limitations

The following legacy UI features are not yet available in the new Cluster Manager UI:

- Remove a node.

    Use the REST API or legacy UI instead. See [Remove a cluster node]({{< relref "/operate/rs/clusters/remove-node" >}}) for instructions.

- Purge an Active-Active instance.

    Use [`crdb-cli crdb purge-instance`]({{< relref "/operate/rs/references/cli-utilities/crdb-cli/crdb/purge-instance" >}}) instead.

- Search and export the log.

#### OpenSSL compatibility issue for 7.4.2 modules on Amazon Linux 2

Due to an OpenSSL 1.1 compatibility issue between modules and clusters, Redis Enterprise Software version 7.4.2-54 is not fully supported on Amazon Linux 2 clusters with databases that use the following modules: RedisGears, RediSearch, or RedisTimeSeries.

This issue will be fixed in a future maintenance release.

#### RedisGraph prevents upgrade to RHEL 9 

You cannot upgrade from a prior RHEL version to RHEL 9 if the Redis Enterprise cluster contains a RedisGraph module, even if unused by any database. The [RedisGraph module has reached End-of-Life](https://redis.com/blog/redisgraph-eol/) and is completely unavailable in RHEL 9.
