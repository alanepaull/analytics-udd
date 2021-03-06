# module_subject
* [MODULE_SUBJECT_ID](#module_subject_id) [1] **
* [MOD_ID](module.md#mod_id) [1] *
* [SUBJECT_ID](#subject_id) [1] *
* [SUBJECT_LABEL](#subject_label) [1]
* [ENCODING_ID](#encoding_id) [1]
* [PROPORTION](#proportion) [0..1]
* [SEQUENCE_ID](#sequence_id) [0..1]
* [PROVIDED_AT](assessment_instance.md#provided_at) [0..1]

\** indicates that the property is the primary key for this entity; if not provided by data supplier, will be Learning Data Hub generated.   
\* indicates that the property is part of a uniqueness constraint for this entity.

## Description of module_subject entity
A module_subject describes the subject or subjects of study of a module, using a specified subject classification system.

## Notes
The design of the module_subject entity follows the design of HESA's Data Futures logical model.

## MODULE_SUBJECT_ID
### Description
Primary key. Where not supplied by data provider, the primary key will be generated by the Learning Data Hub loading mechanism.

### Purpose
Unique identifier for the entity

### Derivation
Jisc

### Valid Values
Any

### Format
String (255)

### Notes
Where not supplied by data provider, the primary key will be generated by the Learning Data Hub loading mechanism.

## SUBJECT_ID
### Description
Code for subject of study

### Purpose
For display and analytical purposes

### Derivation
https://www.hesa.ac.uk/collection/c18051/a/modsbj
https://www.hesa.ac.uk/support/documentation/jacs
https://www.hesa.ac.uk/files/HECoS-Vocabulary_2016-07-28.xlsx

### Valid Values
[JACS3 CSV](../media/jacs3-valid-entries.csv)
[HECOS CSV](../media/HECoS-Vocabulary.csv)

### Format
String (10) - JACS: 4 characters, number followed by three digits; HECoS: 6 digits

### Notes
If a module is associated with multiple subject codes, the same subject coding scheme must be used for all codes. Typically this will be either JACS3 or, in the future, HECoS. 
Omitting this property could impair the functionality of analytics applications such as student apps or dashboards.

## SUBJECT_LABEL
### Description
Human readable name for the subject of study

### Purpose
For display purposes

### Derivation
https://www.hesa.ac.uk/collection/c18051/a/modsbj
https://www.hesa.ac.uk/support/documentation/jacs
https://www.hesa.ac.uk/files/HECoS-Vocabulary_2016-07-28.xlsx

### Valid Values
[JACS3 CSV](../media/jacs3-valid-entries.csv)
[HECOS CSV](../media/HECoS-Vocabulary.csv)

### Format
String (255)

### Notes


## ENCODING_ID

### Description
Prescribed name of the subject of study classification system used in SUBJECT_ID

### Purpose
To indicate the subject of study classification system used.

### Derivation
Jisc

### Valid Values
<table>
 <tr>
  <td>ENCODING_ID</td>
  <td>DESCRIPTION (ENGLISH)</td>
  <td>DESCRIPTION (WELSH)</td>
 </tr>
 <tr>
  <td>JACS3</td>
  <td>Joint Academic Coding System, version 3</td>
  <td></td>
 </tr>
 <tr>
  <td>HECoS</td>
  <td>Higher Education Classification of Subjects</td>
  <td></td>
 </tr>
</table>

### Format
String (255)

### Notes
Additional encoding schemes may be added to Valid Values in the future.

## PROPORTION
### Description
This property shows the weighting of the subject of study as a percentage of the study load.

### Purpose
For display and analytical purposes

### Derivation
HESA Data Futures, https://www.hesa.ac.uk/files/Collection%20Design%20Logical%20Model.pdf

### Valid Values
0-100

### Format
Decimal

### Notes
The value represents a percentage. The total value of all PROPORTION properties for a single module should be 100.
This property was historically referred to in HESA documentation as "weighting".

## SEQUENCE_ID
### Description
Where there is more than 1 module_subject record for a module, this property indicates the order of importance of each subject. More important subjects have lower numbers; for example, the subject with value "1" is the most important.

### Purpose
For display and analytical purposes

### Derivation
Jisc

### Valid Values
Positive integer

### Format
Integer

### Notes
Typically used where it is necessary to use more than 1 subject of study to describe a module adequately.
