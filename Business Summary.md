
# Hospital Readmissions Analysis — Business Summary

## Business Question

Which patient segments have elevated readmission rates, and what operational factors
(age, admitting specialty, length of stay) should hospital administrators focus on to
reduce readmissions?

## Method

Analyzed 25,000 hospital stay records using Excel pivot tables and a Power BI dashboard,
calculating readmission rate across patient age bracket, admitting medical specialty, and
length of hospital stay.

## Key Findings

1. **Overall readmission rate is 47.02%.** Note: this is substantially higher than
   typical real-world hospital readmission rates (commonly 10-20%), suggesting this
   dataset was deliberately balanced for analytical/modeling purposes rather than
   reflecting a raw, naturally-occurring patient population. Findings below should be
   read as relative comparisons between segments, not as real-world absolute rates.
2. **Readmission rate rises steadily with age, then drops for the oldest patients.**
   Rate climbs from 44.5% (ages 40-50) to a peak of 49.6% (ages 80-90), before dropping
   to 42.1% for ages 90-100 — a group that may represent a healthier surviving subset or
   simply a smaller, noisier sample.
3. **Medical specialty shows a meaningful 8.3 percentage point spread.**
   Family/GeneralPractice (49.5%) and Emergency/Trauma (49.4%) have the highest
   readmission rates; Surgery (41.2%) has the lowest. This likely reflects that surgical
   stays often resolve a single, discrete issue, while general/family practice and
   emergency admissions more often involve chronic or multi-factorial conditions.
4. **Readmission risk rises with length of stay, peaking at 7-9 days.** Patients
   discharged within 1-3 days have a 44.3% readmission rate, rising to 50.7% for those
   staying 7-9 days, before easing slightly to 46.2% for the longest stays (13-15 days).

## Recommendation

- **Prioritize discharge planning review for patients approaching or exceeding a 7-day
  stay**, since this group shows the highest readmission risk.
- **Focus additional follow-up care coordination on Family/GeneralPractice and
  Emergency/Trauma admissions**, given their consistently higher readmission rates
  relative to Surgery.
- **Pay particular attention to patients aged 70-90**, who show the highest age-related
  readmission risk.

## Limitations

- The unusually high 47% baseline readmission rate suggests this dataset may be
  artificially balanced rather than representative of a real hospital population;
  absolute percentages should not be generalized outside this dataset.
- The dataset does not include discharge destination detail, insurance type, or
  post-discharge follow-up compliance, all of which likely influence real readmission risk.
