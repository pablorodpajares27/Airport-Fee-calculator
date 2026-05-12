# Workflow

This document describes the complete workflow of the Airport Fee Calculator prototype.

---

## Step 1 — Organize Airport Documentation

Airport fee documents are stored in a folder structure organized by country and airport.

```text
Fees/
  Croatia/
    Dubrovnik/
      airport_fee_document.pdf
  Italy/
    Ciampino/
      airport_fee_document.pdf
```

---

## Step 2 — Process PDF Documents

The first program detects the available PDFs, normalizes the file names and extracts the readable text.

It also generates a customized AI prompt containing the airport name, country, source file name and expected JSON output name.

---

## Step 3 — AI-Assisted Structuring

The generated prompt is used to convert the airport fee documentation into structured JSON.

The JSON is expected to represent user inputs, calculation variables, conditions, formulas, fee components and final outputs.

---

## Step 4 — Validate and Store JSON

The JSON processor validates that the generated file belongs to the selected airport and country.

If the validation is successful, the JSON is saved in the corresponding airport folder.

---

## Step 5 — Run the Fee Calculator

The fee calculator allows the user to select a country and airport.

Once selected, it opens the official airport PDFs, loads the structured JSON, asks the required inputs, runs the calculation engine and prints a detailed fee breakdown.

---

## Step 6 — Review Fee Breakdown

The output is designed to be transparent.

Instead of only displaying a final number, the calculator shows each charge component separately.

```text
=== FEE BREAKDOWN ===
- landing_takeoff_fee: 1636.80
- adult_passenger_fee: 847.00
- child_passenger_fee: 84.20
- security_fee: 79.40
- cargo_fee: 8.30

=== CALCULATION FINISHED ===
total_final: 2899.50
```
