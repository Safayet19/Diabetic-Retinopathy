Update the declaration and submission-information sections of my diabetic retinopathy research project according to the **official PLOS ONE LaTeX template and submission guidelines**.

Work with the CURRENT version of `main.tex`. Do not regenerate the manuscript or overwrite previous modifications.

### 1. Data availability

Locate the existing "Data availability" section. Remove the unrelated kidney CT dataset information and replace it with the following:

**Data availability**

The retinal fundus image datasets used in this study are accessible from their respective providers, subject to applicable access and usage conditions. APTOS 2019 is available through Kaggle (https://www.kaggle.com/competitions/aptos2019-blindness-detection/data), IDRiD through IEEE DataPort (https://ieee-dataport.org/open-access/indian-diabetic-retinopathy-image-dataset-idrid), and Messidor-2 through ADCIS (https://www.adcis.net/en/third-party/messidor2/). The five-grade Messidor-2 dataset used in this study was obtained from the processed RETFound benchmark resource (https://github.com/rmaphoh/RETFound/blob/main/BENCHMARK.md); the official Messidor-2 release does not contain DR severity annotations.

The research implementation notebooks are publicly available at https://github.com/Safayet19/Diabetic-Retinopathy. Original dataset images are not redistributed in this repository.

Verify that the links are valid and that the repository description accurately reflects its contents. Do not invent dataset accessions, DOIs, supplementary data, or reproducibility claims.

### 2. Author contributions

Retain the existing CRediT author contribution assignments exactly as provided below. The only name correction is replacing "Md. Mijanur Rahman" with "Abdul Kadar Muhammad Masum".

**Author contributions**

Conceptualization: Abdul Kadar Muhammad Masum.

Data curation: Safayet Ullah, Md. Jubayer Islam, Tanvirul Hoque Faysal.

Formal analysis: Abdul Kadar Muhammad Masum, Safayet Ullah.

Investigation: Safayet Ullah, Md. Jubayer Islam.

Methodology: Safayet Ullah, Md. Jubayer Islam.

Resources: Abdul Kadar Muhammad Masum.

Software: Safayet Ullah.

Supervision: Abdul Kadar Muhammad Masum.

Validation: Safayet Ullah, Md. Jubayer Islam, Tanvirul Hoque Faysal.

Visualization: Safayet Ullah, Md. Jubayer Islam.

Writing – original draft: Safayet Ullah, Md. Jubayer Islam, Tanvirul Hoque Faysal.

Writing – review & editing: Abdul Kadar Muhammad Masum, Safayet Ullah.

Preserve all 12 contribution categories and their assigned authors. Do not invent additional roles or change existing responsibilities.

According to PLOS ONE, these contributions must be entered in the submission system. Keep them in a separate `SUBMISSION_METADATA.md` file for submission entry rather than adding unnecessary sections to the manuscript PDF.

### 3. Competing interests

Prepare the following declaration for the PLOS ONE submission system:

"The authors declare that they have no competing interests."

This declaration must be confirmed by all four authors before submission.

According to the official PLOS ONE guidelines, competing interests must be declared through the submission system and should not be included in the manuscript PDF.

Therefore:
- Remove any "Competing interests" section from `main.tex`.
- Preserve the declaration in `SUBMISSION_METADATA.md`.
- Do not invent financial, institutional, personal, or commercial relationships.

### 4. Acknowledgments

Keep the Acknowledgments section immediately before References, as required by PLOS ONE.

Retain any genuine existing acknowledgments. Do not invent acknowledgments or individuals.

Check the official Messidor-2 dataset attribution requirements against its provider documentation and identify any mandatory acknowledgments or citations that are missing. Do not fabricate acknowledgment text.

Do not place funding declarations in Acknowledgments; PLOS ONE collects funding information separately through the submission system.

### 5. Formatting and placement

- Follow the official PLOS ONE LaTeX template.
- Retain the Data availability section and its verified content in the manuscript, without creating duplicate sections.
- Keep Acknowledgments immediately before References.
- Keep Author contributions and Competing interests in the separate submission metadata file rather than inserting them into the manuscript PDF.
- Preserve the current font, margins, line spacing, section styling, and continuous line numbering.
- Keep URLs clickable and allow proper line wrapping.
- Do not modify any research results, equations, tables, figures, citations, bibliography entries, or scientific statements.
- Do not rewrite the entire `main.tex`.

### 6. Final verification

After making these targeted changes:

1. Compile `main.tex` successfully.
2. Verify that the kidney CT information is completely removed.
3. Confirm all three DR datasets and the GitHub repository are correctly described.
4. Confirm that all 12 CRediT roles are preserved and the supervisor's name is corrected everywhere in the contribution statement.
5. Confirm the competing-interest declaration is available in `SUBMISSION_METADATA.md`, not the manuscript PDF.
6. Verify Acknowledgments and References are in the correct order.
7. Check that no content, citations, equations, tables, figures, or formatting outside the requested sections was changed.

Report any unverified information explicitly instead of guessing. Apply only the requested modifications.
