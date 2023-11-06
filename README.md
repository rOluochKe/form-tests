# Updating Form Creation Tests for OpenMRS ESM Form Builder

## Objective

The objective is to enhance the existing form creation tests for the OpenMRS ESM Form Builder to ensure that all form saving details, such as form name, encounter type, and version, are correctly saved and verified.

## Solution

To achieve this, I made modifications to the existing test files, specifically `create-form-using-dummy-schema.spec.ts` and `create-form-using-custom-schema.spec.ts.` Below are the steps to update these tests:

### Step 1: Add Assertions to Check Form Saving Details

In both test files (`create-form-using-dummy-schema.spec.ts` and `create-form-using-custom-schema.spec.ts.`), add assertions to check whether the form saving details are correctly saved. You can add these assertions after saving the form. For example:

    ```bash
    const formVersionValue = await formBuilderPage.formVersionInput().inputValue();
    const formDescriptionValue = await formBuilderPage.formDescriptionInput().inputValue();
    const formEncounterTypeValue = await formBuilderPage.formEncounterType().inputValue();

    expect(formNameValue).toContain('A sample test form');
    expect(formVersionValue).toBe('1.0');
    expect(formDescriptionValue).toBe('This is a test form');
    expect(formEncounterTypeValue).toBe('Admission');
    ```

### Step 2: Update the tests

1. Clone the OpenMRS ESM Form Builder repository if you haven't already:

    `git clone https://github.com/openmrs/openmrs-esm-form-builder.git`

2. Navigate to the E2E tests directory:

    `cd openmrs-esm-form-builder/e2e`

3. Update the two files and run tests

    `yarn turbo test`