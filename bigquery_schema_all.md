# BigQuery schema reference (Stanford GPS)

## Index
- [Dataset: gps_stanford_clinic](#dataset-gps_stanford_clinic)
  - [cohort_iop_adult](#cohort_iop_adult)
  - [cohort_systemic](#cohort_systemic)
  - [mrn_crosswalk](#mrn_crosswalk)
  - [person](#person)
  - [measurement](#measurement)
  - [condition_occurrence](#condition_occurrence)
  - [procedure_occurrence](#procedure_occurrence)
  - [drug_era](#drug_era)
- [Dataset: SOURCE](#dataset-source)
  - [sf_oph_enc_exam](#sf_oph_enc_exam)
  - [sf_oph_med](#sf_oph_med)
  - [sf_oph_surgery_all](#sf_oph_surgery_all)

---

## Dataset: gps_stanford_clinic

### cohort_iop_adult 
Schema:
- `pat_mrn` STRING
- `first_iop_date` DATETIME
- `age_at_iop` FLOAT

### cohort_systemic
Schema:
- `rand_num` INTEGER
- `pat_mrn` STRING
- `first_iop_date` DATETIME

### mrn_crosswalk
Schema:
- `person_id` INTEGER
- `MRN` STRING
- `source_dob` STRING

### person
Schema (OMOP CDM):
- `person_id` INTEGER
- `gender_concept_id` INTEGER
- `year_of_birth` INTEGER
- `month_of_birth` INTEGER
- `day_of_birth` INTEGER
- `birth_datetime` DATETIME
- `race_concept_id` INTEGER
- `ethnicity_concept_id` INTEGER
- `location_id` INTEGER
- `provider_id` INTEGER
- `care_site_id` INTEGER
- `person_source_value` STRING
- `gender_source_value` STRING
- `gender_source_concept_id` INTEGER
- `race_source_value` STRING
- `race_source_concept_id` INTEGER
- `ethnicity_source_value` STRING
- `ethnicity_source_concept_id` INTEGER

### measurement
Schema (OMOP CDM):
- `measurement_id` INTEGER
- `person_id` INTEGER
- `measurement_concept_id` INTEGER
- `measurement_date` DATE
- `measurement_datetime` DATETIME
- `measurement_time` STRING
- `measurement_type_concept_id` INTEGER
- `operator_concept_id` INTEGER
- `value_as_number` FLOAT
- `value_as_concept_id` INTEGER
- `unit_concept_id` INTEGER
- `range_low` FLOAT
- `range_high` FLOAT
- `provider_id` INTEGER
- `visit_occurrence_id` INTEGER
- `visit_detail_id` INTEGER
- `measurement_source_value` STRING
- `measurement_source_concept_id` INTEGER
- `unit_source_value` STRING
- `value_source_value` STRING

### condition_occurrence
Schema (OMOP CDM):
- `condition_occurrence_id` INTEGER
- `person_id` INTEGER
- `condition_concept_id` INTEGER
- `condition_start_date` DATE
- `condition_start_datetime` DATETIME
- `condition_end_date` DATE
- `condition_end_datetime` DATETIME
- `condition_type_concept_id` INTEGER
- `condition_status_concept_id` INTEGER
- `stop_reason` STRING
- `provider_id` INTEGER
- `visit_occurrence_id` INTEGER
- `visit_detail_id` INTEGER
- `condition_source_value` STRING
- `condition_source_concept_id` INTEGER
- `condition_status_source_value` STRING

### procedure_occurrence
Schema (OMOP CDM):
- `procedure_occurrence_id` INTEGER
- `person_id` INTEGER
- `procedure_concept_id` INTEGER
- `procedure_date` DATE
- `procedure_datetime` DATETIME
- `procedure_type_concept_id` INTEGER
- `modifier_concept_id` INTEGER
- `quantity` INTEGER
- `provider_id` INTEGER
- `visit_occurrence_id` INTEGER
- `visit_detail_id` INTEGER
- `procedure_source_value` STRING
- `procedure_source_concept_id` INTEGER
- `modifier_source_value` STRING

### drug_era
Schema (OMOP CDM):
- `drug_era_id` INTEGER
- `person_id` INTEGER
- `drug_concept_id` INTEGER
- `drug_era_start_date` DATE
- `drug_era_end_date` DATE
- `drug_exposure_count` INTEGER
- `gap_days` INTEGER

---

## Dataset: SOURCE

### sf_oph_enc_exam
Schema:
- `concept_id` STRING
- `concept_name` STRING
- `pat_mrn` STRING
- `pat_id` STRING
- `pat_enc_csn_id` INTEGER
- `cur_value_datetime` DATETIME
- `element_value_id` INTEGER
- `line` INTEGER
- `smrtdta_elem_value` STRING
- `contact_date` DATETIME

### sf_oph_med
Schema:
- `order_med_id` INTEGER
- `pat_mrn` STRING
- `pat_id` STRING
- `PAT_ENC_CSN_ID` INTEGER
- `order_status` STRING
- `MED_PRESC_PROV_name` STRING
- `ordering_dttm` DATETIME
- `order_start_time` DATETIME
- `order_end_time` DATETIME
- `discontinue_datetime` DATETIME
- `NAME` STRING
- `generic` STRING
- `therapeutic_class` STRING
- `pharmaceutical_class` STRING
- `strength` STRING
- `med_dose_unit` STRING
- `admin_dose_unit` STRING
- `med_route` STRING
- `hv_discrete_dose` STRING
- `quantity` STRING
- `MED_DISP_QTY` NUMERIC
- `Total_doses` INTEGER
- `total_remaining_doses` INTEGER
- `refills` STRING
- `instruction` STRING
- `frequency` STRING
- `pat_enc_date_real` NUMERIC
- `medication_id` INTEGER
- `MED_PRESC_PROV_ID` STRING
- `gpi` STRING
- `med_route_c` INTEGER
- `hv_dose_unit_c` INTEGER
- `max_dose_unit_c` INTEGER
- `order_status_c` INTEGER
- `HV_DISCR_FREQ_ID` STRING
- `PHARMACY_ID` INTEGER
- `DISP_AS_WRITTEN_YN` STRING
- `RSN_FOR_DISCON` STRING
- `EXT_FORMULARY_ID` STRING
- `EXT_COVERAGE_ID` STRING
- `EXT_COPAY_ID` STRING
- `EXT_PHARMACY_TYPE` STRING
- `EXT_FORMULARY_STAT` STRING
- `cost` STRING

### sf_oph_surgery_all
Schema:
- `pat_mrn` STRING
- `pat_id` STRING
- `SURGERY_CSN_ID` INTEGER
- `PAT_ENC_CSN_ID` INTEGER
- `CASE_ID` STRING
- `log_id` STRING
- `NUM_OF_PANELS` INTEGER
- `PRE_OP_DIAG` STRING
- `OR_POSTOP_DEST` STRING
- `HSP_ACCOUNT_ID` INTEGER
- `patient_class` STRING
- `PATIENT_TYPE_CD` STRING
- `or_service` STRING
- `LOCATION` STRING
- `ROOM` STRING
- `OR_STATUS` STRING
- `OR_ANESTH_TYPE` STRING
- `OR_Laterality` STRING
- `site` STRING
- `incision_closure` STRING
- `OR_WOUND_CLASS` STRING
- `primary_physician` STRING
- `ANESTHESIOLOGIST` STRING
- `PNL_1_PRIM_PROC_NM` STRING
- `ALL_PROC_AS_ORDERED` STRING
- `TOTAL_TIME_NEEDED` INTEGER
- `SCHED_START_TIME` DATETIME
- `PREOP_PRESENT_datetime` DATETIME
- `RN_ASSESS_COMPLETE_datetime` DATETIME
- `Room_Ready_datetime` DATETIME
- `Pat_In_OR_datetime` DATETIME
- `Incision_Start_datetime` DATETIME
- `Dressing_End_datetime` DATETIME
- `Out_or_datetime` DATETIME
- `COMPLETE_datetime` DATETIME
- `INPATIENT_DATA_ID` STRING
- `service_c` STRING
- `PNL_1_PRIM_PROC_EXT_ID` STRING
- `PNL_1_PRIM_SURG_PROC_ID` STRING
- `PRIMARY_PHYS_ID` STRING
- `ANES_prov_id` STRING
- `cpt1` STRING
- `cpt2` STRING
- `cpt3` STRING
- `cpt4` STRING
- `cpt5` STRING
- `mod1` STRING
- `mod2` STRING
- `mod3` STRING
- `mod4` STRING
- `mod5` STRING

