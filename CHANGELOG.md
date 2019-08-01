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


## [1.5.8.1]
### Added
- The following new HL7v3 releases are now supported in Message Builder:
  - AB MR2009 R02.04.03 Client Registry and Provider Registry
  - AB MR2009 R02.04.03 Immunization
  - pan-Canadian MR 02.05
  - pan-Canadian CeRx 4.4
- 20423 - created an interaction walker (Java only)


### Changed
- 20416 - URG changes for BC


### Removed
- unused interactions for AB MR2007 and AB MR2009


## [1.5.8]
### Added
- created a Sample Message Generator (Java only) that uses a generated MB API to create a sample message for a specific interaction or for all interactions
- added new official MB API releases: V01R04.4; R02.05.00; AB PA R02.05.00
- 17375 - Add support for EN abstract datatype
- 18989 - Create a message set validator
- 18988 - Create a utility for checking message sets for "orphaned" message parts

### Fixed
- 18979 - Complex relationship sorting duplicated in three places
- 16129 - Message Bean Transformer for unmarshalling xml (xml -> beans) does not validate cardinality for associations
- 16132 - Unmarshalling xml (xml -> beans) does not validate against relationships that are out of order
- 16130 - Message Bean Transformer for marshalling xml (beans -> xml) does not validate cardinality for associations
- 16131 - Message validator does not validate order of relationships within an element
- 18719 - ST should be able to handle CDATA blocks
- 18070 - When an ANY type is set as a NullFlavor, originalText is not preserved
- 18423 - MB runtime should not necessarily log an error when SpecializationType is unnecessarily provided
- 18422 - MB Runtime should not throw an exception in a situation where logging an error would be more appropriate
- 18323 - Domain type package location is effectively still hardcoded in one place
- 16399 - TS.FULLDATEWITHTIME formatter will incorrectly flag a validation error when no value specified and relationship is not mandatory


## [1.5.6]
### Added
- 16697 [DB RESOLVER] Provide a code demo for the new DB Resolver changes, utilizing an in-memory database
- 17372 [.NET] implement Database Resolver registration utility in .NET
- 18202 [BC] New dataype SC - and alias, SC.CA
- 18194 [BC] Add alias for ST.CA
- 18195 [BC] Add alias for CS.CA
- 18196 [BC] Add alias for CV.CA
- 18197 [BC] implement ANY.x1 and ANY.x2
- 18198 [BC] create new datatype TS.FULLDATEPARTTIME
- 18201 [BC] Implement a cross-release approach to datatype validations
- 18203 [BC] add displayName to CV/CV.CA


### Fixed
- 17048 BC: Parsing issue with HL7 sensitivityObservationEvent
- 17316 Store the release Realm Code and Descriptive Name in a MessageSet
- 17371 [.NET] manual translation required for VocabularyDomain.getTypeAsClasses()
- 17421 Validation errors with no xpath
- 17477 Assigning different colors and adding CSS class for the vocab SVG diagrams
- 17511 Invalid Concept Domains are defined in Message Set
- 18049 Capture concept status from MIF to Message Set
- 18531 [.NET] datatypes are not implementing Equals() correctly


### Removed
- 17524 Remove Java class assignment from Message Set


## [1.5.0]
### Added
- 14452 - Create a Message Builder Java API for ON Drug Message Set
- 14453 - Create a Message Builder .NET API for ON Drug Message Set
- 14561 - Create a helper method for setting specialization type on a collection
- 14581 - Create helper methods for setting null flavor on a collection

### Changed
- All MB message sets and APIs have been re-generated to accomodate Message Remixer v3 changes
  - Some minor coding changes may be required for clients using a MB API as a result of the re-gens


### Fixed
- 14377 - FW: Infoway message builder API 1.4.6 problem [`IVL<TS.FULLDATETIME>` could not be properly specified for an `ANY` type]
- 14562 - CodedString datatype (SC) does not generate properly (not a pan-Canadian standard datatype)
- 14612 - Unexpected console output from MessageBeanTransformerImpl
- 14620 - DRUG_DOCUMENT_QUERY and DRUG_DOCUMENT_QUERY_RESPONSE missing from Ca.Infoway.Messagebuilder.Domainvalue.Transport.HL7TriggerEventCode
- 14644 - Unable to read a message (Can't find a relationship named : component1 on messa gePart named POLB_MT004200BC.ObservationReport) [a Remixer had affected the sort of message elements in rendered xml]
- 14740 - Some formatters and parsers will break when dealing with values provided though the ANY datatype
- 15236 - argument type mismatch [the ActMood enum implemented the ActCode interface instead of the ActMood interface]
- 15390 - Could not find coded value for domain type x_ActMoodDefEvnRqo [the Terminology component had a bug with fixed or CS codes]
- 15393 - Errors validating combinedMedicationRequest.subjectOf3.rxOrderType.moodCode [same as 15390]
- 15395 - Cardinality for telecom fields not validated. [Cardinality now validated for all attribute collections]
- 15419 - no exception if duplicates were specified for the SET<> datatype
- 15431 - MANDATORY_FIELD_NOT_PROVIDED: Attribute "id" is required, but is specified as nullFlavor="NI". [MB now allows NF for all conformances except MANDATORY]
- 15446 - java.lang.ClassCastException [this was caused by a complex generator bug]
- 15915 - Crash in MessageBuilder while generating a Message Set when a vocabulary MIF contains <excludeContent>
filters based on <propertyBasedContent>
- 15929 - MB-generated message does not pass XSD validation [IVL and URG inner elements did not have the correct xsi:type]


## Removed
- 14626 - Drop support for MR2007 V02R01 in Message Builder


## [1.4.6]
HERE I AM!!

