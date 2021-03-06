# SUBPART
ISPF Edit Command (Macro) to  Submit a subset of data lines for batch processing.

## INTRODUCTION

**SUBPART** is an ISPF Edit command (macro) to submit JCL to the Internal Reader
for batch processing, and is intended for datasets with LRECL > 80 as the IBM
ISPF Edit Submit supports all but the 1st# and last# options of SUBPART.  It
allows for the selection of which data records are to be submitted.

Syntax:    subpart                 (with lines selected)
         or subpart 1st# last#     (e.g. 3 21)
         or subpart 1stlab lastlab (e.g. .a .b)
         or subpart nx             (non-excluded records)
         or subpart *              (all records)
         or subpart ?              (tutorial)
         or subpart                (tutorial)

Data Line Selection is by excluding those lines that are not to be submitted
and then use subpart nx or selecting the desired lines using **SS** or **S#**.

Note: By excluding the lines not to submit the desired lines do not have to
be contiguous.

## INSTALLATION

Copy the SUBPART member, which is the REXX exec, into a library in your
SYSEXEC, or SYSPROC, allocations.

## USE CASES

Case 1: Utility JOB
        Have records with different utilty functions and only submit
        the desired function without having multiple members for each
        function, or without having to delete all functions except the
        desired one.

Case 2: Verification Jobs
        All shipped in the same PDS member but you only want to submit
        one, or a few, of the jobs.

Case 3: Compile, Link, Test JOB
        Submit only the Compile part of the job, or just the Compile and
        Link, or just the Test part of the job.
