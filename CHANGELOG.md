# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2019-09-18

### Changed
* Return version tuple from get_protocol_version methods [#154](https://github.com/greenbone/python-gvm/pull/154)

### Fixed
* Fixed `create_tag` and `modify_tag` `resource_type` argument to expect an
  EntityType in `Gmp8` [PR 150](https://github.com/greenbone/python-gvm/pull/150)
* Re-added `SMB` as an allowed `AlertMethod` for SecInfo events
  [PR 145](https://github.com/greenbone/python-gvm/pull/145)

[1.0.0]: https://github.com/greenbone/python-gvm/compare/v1.0.0.beta3...v1.0.0

## [1.0.0.beta3] - 2019-07-30

### Added
* Added preferences argument to `create_task` method [PR 89](https://github.com/greenbone/python-gvm/pull/89)
* Added validation of alive_tests argument to `create_target` method [PR 88](https://github.com/greenbone/python-gvm/pull/88)
* Added ssh_credential_port argument to `modify_target` [PR 88](https://github.com/greenbone/python-gvm/pull/88)
* Split getting a single preference by name from `get_preferences` method into
  `get_preference` [PR 85](https://github.com/greenbone/python-gvm/pull/85)
* Added resource_type argument to `get_aggregates` method [PR 107](https://github.com/greenbone/python-gvm/pull/107)
* Added an explicit `create_container_task` method [PR 108](https://github.com/greenbone/python-gvm/pull/108)
* Added Gmpv8 version of create_tag with resource_filter parameter and
  plural resource_ids parameter [PR 115](https://github.com/greenbone/python-gvm/pull/115)
* Added Gmpv8 version of modify_tag with resource_action parameter,
  resource_filter parameter, plural resource_ids parameter [PR 115](https://github.com/greenbone/python-gvm/pull/115)
* Added no_details argument to `get_reports` method [PR 129](https://github.com/greenbone/python-gvm/pull/129)
* Added `get_vulnerabilites` method [PR 132](https://github.com/greenbone/python-gvm/pull/132)
* Added `get_ticket`, `get_tickets`, `create_ticket`, `clone_ticket`, `modify_ticket` and `delete_ticket`
  APIs to GMPv8 [PR 132](https://github.com/greenbone/python-gvm/pull/132)
* Added filter types for `host`, `operating system`, `ticket` and `vulnerability`
  [PR 133](https://github.com/greenbone/python-gvm/pull/133)
* Added a `password only` credential type [PR 133](https://github.com/greenbone/python-gvm/pull/133)
* Added [type hints](https://docs.python.org/3/library/typing.html) for Gmpv8
  [PR 136](https://github.com/greenbone/python-gvm/pull/136)
* Added dynamic selection of the Gmp class depending on the GMP version supported
  by the remote manager daemon
  [PR 141](https://github.com/greenbone/python-gvm/pull/141)
* Added all types as types property to the Gmp classes (e.g gmp.types.EntityType.TASK)
  [PR 143](https://github.com/greenbone/python-gvm/pull/143)

### Changed
* Renamed `create_asset` method to `create_host` and dropped asset_type
  argument. It is only possible to create host assets. [PR 77](https://github.com/greenbone/python-gvm/pull/77)
* Require either setting_id or name for `modify_setting` not both arguments [PR 87](https://github.com/greenbone/python-gvm/pull/87)
* Allow empty string as value argument for `modify_setting` [PR 87](https://github.com/greenbone/python-gvm/pull/87)
* Require either user_id or name for `modify_user` not both arguments [PR 87](https://github.com/greenbone/python-gvm/pull/87)
* Updated argument types for `create_note`, `create_override`, `modify_note`
  and `modify_override` [PR 87](https://github.com/greenbone/python-gvm/pull/87)
* The arguments threat (and new_threat) for `create_note`, `modify_note`,
  `create_override` and `modify_override` must be one of 'High', 'Medium',
  'Low', 'Alarm', 'Log' or 'Debug' now [PR 87](https://github.com/greenbone/python-gvm/pull/87)
* Allow to pass either user_id or name to `delete_user` [PR 88](https://github.com/greenbone/python-gvm/pull/88)
* Don't require inheritor_id or inheritor_name for `delete_user`
* Don't require ca_pub for `create_scanner` [PR 88](https://github.com/greenbone/python-gvm/pull/88)
* Change port argument for `create_scanner` to be an integer [PR 88](https://github.com/greenbone/python-gvm/pull/88)
* Refactor `modify_scanner` method: Adjust argument types corresponding to
 `create_scanner` and only require scanner_id [PR 88](https://github.com/greenbone/python-gvm/pull/88)
* Updated and improved validation of `create_schedule` and
  `modify_schedule` arguments [PR 89](https://github.com/greenbone/python-gvm/pull/89)
* Refactor `modify_task` to use same arguments as `create_task` [PR 89](https://github.com/greenbone/python-gvm/pull/89)
* Aligned ALIVE_TESTS declaration with list from GSA [PR 93](https://github.com/greenbone/python-gvm/pull/93)
* Address DeprecationWarning regarding `collections` module [PR 99](https://github.com/greenbone/python-gvm/pull/99)
* Forbid *'0'* as target_id value for  `create_task` method and move creating a
  container task into an own method [PR 108](https://github.com/greenbone/python-gvm/pull/108)
* Refresh the dependencies specified via the Pipfile.lock file to their latest
  versions [PR 113](https://github.com/greenbone/python-gvm/pull/113),
  [PR 131](https://github.com/greenbone/python-gvm/pull/131)
* Make resource_id optional when creating tags (Gmpv7) [PR 124](https://github.com/greenbone/python-gvm/pull/124)
* Allow creating tags without resource (Gmpv8) [PR 125](https://github.com/greenbone/python-gvm/pull/125)
* Adapt modify_tag validation to actual implementation (Gmpv8) [PR 127](https://github.com/greenbone/python-gvm/pull/127)
* Use Gmpv8 as latest Gmp version [PR 132](https://github.com/greenbone/python-gvm/pull/132)
* Dropped the `make_unique` arguments from `create_filter` and `create_target`
  methods in Gmpv8 [PR 133](https://github.com/greenbone/python-gvm/pull/133)
* Introduced Enum classes for authentication and privacy algorithms of SNMP
  credentials [PR 133](https://github.com/greenbone/python-gvm/pull/133)
* Extended `InvalidArgument` and `RequiredArgument` errors to allow passing
  argument and function name as keyword parameter [PR 134](https://github.com/greenbone/python-gvm/pull/134)
* Renamed `modify_target` and `create_target` argument `alive_tests` to `alive_test`
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use [enum](https://docs.python.org/3/library/enum.html) AliveTests for
  `alive_test` arguments
  [PR 136](https://github.com/greenbone/python-gvm/pull/136)
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `AlertCondition`, `AlertEvent` and `AlertMethod` enums for `create_alert`
  and `modify_alert` methods
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `AssetType` enum for `get_asset` and `get_assets` method
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `CredentialFormat` enum for `get_credential` method
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `CredentialType` enum for `create_credential` and `modify_credential`
  methods
  [PR 132](https://github.com/greenbone/python-gvm/pull/132)
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `EntityType` enum for `create_permission`, `create_tag`, `get_aggregates`,
  `modify_permission` and `modify_tag` methods
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `FeedType` enum for `get_feed` method
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `FilterType` enum for `create_filter` and `modify_filter` method
  [PR 133](https://github.com/greenbone/python-gvm/pull/133)
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `HostsOrdering` enum for `create_task` and `modify_task` method
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `InfoType` enum for `get_info` and `get_info_list` methods
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `PermissionSubjectType` enum for `create_permission` and
  `modify_permission` methods
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `PortRangeType` enum for `create_port_range` method
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `ScannerType` enum for `create_scanner` and `modify_scanner` methods
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `SnmpAuthAlgorithm` and `SnmpPrivacyAlgorithm` enums for `create_credential`
  and `modify_credential` methods
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `SeverityLevel` enum for `create_note`, `create_override`, `modify_note`
  and `modify_override` methods
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Use new `TimeUnit` enum for `create_schedule` and `modify_schedule` methods
  [PR 139](https://github.com/greenbone/python-gvm/pull/139)
* Update `create_schedule` and `modify_schedule` in `Gmpv8` to use
  [iCalendar](https://tools.ietf.org/html/rfc5545) based data for schedules
  [PR 140](https://github.com/greenbone/python-gvm/pull/140)

### Removed
* Removed the format parameter from `get_credentials` method [PR 85](https://github.com/greenbone/python-gvm/pull/85)
* Removed the task_id and nvt_oid parameters from `get_notes` and
  `get_overrides` methods [PR 85](https://github.com/greenbone/python-gvm/pull/85)
* Removed sources argument from `modify_user` method [PR 87](https://github.com/greenbone/python-gvm/pull/87)
* Removed `modify_report` method [PR 87](https://github.com/greenbone/python-gvm/pull/87)
* Removed unused comment argument from `create_note` and `create_override` [PR 87](https://github.com/greenbone/python-gvm/pull/87)
* Removed hosts_ordering argument from `modify_target` [PR 88](https://github.com/greenbone/python-gvm/pull/88)
* Excluded tests from installation [PR 119](https://github.com/greenbone/python-gvm/pull/119)
* Removed `credential_type` argument from `modify_credential` [PR 139](https://github.com/greenbone/python-gvm/pull/139)

### Fixed
* Fixed generating XML for `get_credentials` command [PR 74](https://github.com/greenbone/python-gvm/pull/74)
* Fixed generating XML for `get_settings` command [PR 80](https://github.com/greenbone/python-gvm/pull/80)
* Fixed generating XML for `get_nvts` command [PR 84](https://github.com/greenbone/python-gvm/pull/84)
* Fixed wrong order of key and value for condition_data, event_data and
  method_data dict parameters of `modify_alert` method [PR 85](https://github.com/greenbone/python-gvm/pull/85)
* Fixed sending resource id in `modify_tag` [PR 88](https://github.com/greenbone/python-gvm/pull/88)
* Ensure `modify_setting` value is send as Base64-encoded [PR 98](https://github.com/greenbone/python-gvm/pull/98)

### Deprecated
* `modify_config` is marked as deprecated and will be removed in future. One of
  the more specific `modify_config_set_` method should be used instead [PR 87](https://github.com/greenbone/python-gvm/pull/87)

[1.0.0.beta3]: https://github.com/greenbone/python-gvm/compare/v1.0.0.beta2...v1.0.0.beta3

## [1.0.0.beta2] - 2018-12-04

### Added
* Added new `trigger_alert` method for triggering an alert method on a
  specific report.
* Added `import_config` method to import a scan config from xml.
* Added helper function to validate xml input `gvm.xml.validate_xml_string`
* Add `finish_send` method to connections. The method allows to indicate to
  the server sending data is finished and no additional data has to be received.

### Changed
* `help` method `type` argument got renamed to `help_type`
* `help` method `help_type` argument will be checked for invalid values
* `create_credential` requires a credential_type argument now.
* Optional arguments are required to be passed as keyword arguments.
* `get_report` method `format_id` argument got renamed to
  `report_format_id`
* Check if scanner_type is one of '1' (OSP Scanner) or '2' (OpenVAS Scanner) in
  `create_scanner` method.
* `pretty_print` accepts a xml string as input too
* Optional arguments for connection class constructors must be passed as
  keyword arguments.
* It's possible to wait indefinitely by deactivating the timeouts via passing
  None as timeout argument to the connection class constructors now.

### Fixed
* Fix: Don't close the connection after each send/read command sequence
  automatically. This fixes sending more then one privileged gmp command after
  authentication.
* Fixed generating XML for help command
* Fixed wrong order of key and value for condition_data, event_data and
  method_data dict parameters of `create_alert` method.
* Fixed `get_reports` sending the wrong protocol command
* Fixed `create_permission` method
* Fixed `get_config` sending the correct protocol command.
* Don't crash if huge content is returned in a xml response. This fixes e.g.
  `get_reports` for bigger report data.

### Removed
* Removed `format_id` argument from get_reports
* Removed `alert_id` argument from `get_reports`
* Removed unused `read_timeout` argument from `UnixSocketConnection`

## [1.0.0.beta1] - 2018-11-13

python-gvm was a part of [gvm-tools](https://github.com/greenbone/gvm-tools)
prior gvm-tools version 2.0. It got extracted from gvm-tools and completely
overhauled.

Some notable changes are:

* The package name changed from *gmp* to *gvm*.
* The type of connection is passed to a more generic Gmp class instead of
  having to select the connection when creating the gmp object.
* Support for different protocols and versions has been added. Currently
  supported protocols are OSP v1 and GMP v7.
* Full API documentation is available at https://python-gvm.readthedocs.io/en/latest/.
* Possible arguments to protocol methods are documented.
* Arguments should be passed as keywords

### Gmp API changes

* `create_report` has been renamed to `import_report`.
* Requesting single entities has been extracted from the list commands e.g.
  `get_task(task_id)` instead of `get_tasks(task_id=task_id)`.
* `get_info` requests a single info entity.
* `get_info_list` requests a list of info entities.
* `filt_id` argument is called `filter_id` at all Gmp methods.
* `report_filter` argument for `get_reports` got renamed to `filter`.
  `report_filt_id` is `filter_id` now.
* `create_schedule` `start_time` and `end_time` arguments got split into
  several parameters.
* Plural arguments like `hosts`, `users`, ... always require a list now.
* `create_alert` `event`, `condition` and `method` arguments got
  revised and split.
* Boolean parameters expect True and False and not 1, 0, '1' or '0' now.
* `get_assets` type parameter got renamed to `asset_type`
* Copying an entity via the `copy` argument has been removed and extracted to
  own `clone` methods e.g. `clone_task`.

[1.0.0.beta2]: https://github.com/greenbone/python-gvm/compare/v1.0.0.beta1...v1.0.0.beta2
[1.0.0.beta1]: https://github.com/greenbone/python-gvm/releases/tag/v1.0.0.beta1
