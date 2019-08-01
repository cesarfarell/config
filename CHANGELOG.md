# Changelog


## [2.1.3]
### Added
- Eight codes to the AcknowledgementDetailCode enumeration to align it with the current terminology definitions
- Validation to ensure all template parameters are populated in interactions


### Changed
- Performance improvements in run-time engine
- Update message sets to explicitly mark attributes
- If you are upgrading from a previous version (i.e., 1.6 or earlier), please be aware of the following:
  - The following classes were moved from `ca.infoway.messagebuilder.datatype.lang.util` and placed in `ca.infoway.messagebuilder.datatype.lang`:
    - `IntervalFactor`
    - `Identifiable`
    - `IntervalFactory`
    - `IntervalUtil`
    - `NameFormatter`
    - `UncertainRangeFactory`
  - The following classes were moved from `ca.infoway.messagebuilder.marshalling.hl7` and placed in `ca.infoway.messagebuilder.error`:
    - `Hl7Error`
    - `Hl7ErrorCode`
    - `Hl7Errors`
  - Other classes in the generated Message Builder HL7v3 runtime libraries may have been moved as well due to internal changes in the Message Builder Generator. Please use an IDE to re-locate those classes and fix the import statements appropriately in your project.


## [2.1.0]
### Added
- .NET APIs for CDA - Consolidated CDA R1_1, Consolidated CDA R1_1 with Canadian data types, pC CDA document with pC CDA header guideline R1_2
- CDA Code Resolver in .NET supporting CCDA R1.1 vocabulary
- MB CDA .NET HelloWorld project


## [2.0.0]
### Added
- Java APIs for CDA - Consolidated CDA R1_1, Consolidated CDA R1_1 with Canadian data types, pC CDA document with pC CDA header guideline R1_2
- CDA Code Resolver supporting CCDA R1.1 vocabulary
- MB CDA HelloWorld project
- CDA R2 datatypes now supported


### Changed
- error classes have moved (to `ca.infoway.messagebuilder.error`)
- errors now include an error level (INFO, WARNING, ERROR)
- major changes to ED datatype (`ca.infoway.messagebuilder.datatype.lang.EncapsulatedData`)
- validator now uses the transformer directly (instead of duplicating code)


## [1.6.0]
### Added
- Support for the following new HL7v3 releases:
  - NS CeRx R04.03 Drug
  - NS MR2009 R02.04.03 Client Registry, Provider Registry and Location Registry
- Two new HelloWorld projects created for NS (CeRx & MR2009)


### Fixed
- MBR-319 - change Message Element Name from NS to CA; resolve `dosageInstruction/@moodCode` value

