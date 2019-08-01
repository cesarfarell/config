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


## [0.3.0] - 2015-12-03
### Added
- RU translation from [@aishek](https://github.com/aishek).
- pt-BR translation from [@tallesl](https://github.com/tallesl).
- es-ES translation from [@ZeliosAriex](https://github.com/ZeliosAriex).
