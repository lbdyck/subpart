# SUBPART
ISPF Edit Command (Macro) to  Submit a subset of data lines for batch processing.

## INTRODUCTION

**SUBPART** is an ISPF Edit command (macro) to submit JCL to the Internal Reader
for batch processing. It allows for the selection of which data records are
to be submitted.

Syntax:    subpart (with lines selected)
        or subpart first last
        or subpart nx
        or subpart ?

Data Line Selection is by excluding those lines that are not to be submitted
and then use subpart nx or selecting the desired lines using **SS** or **S#**.

Note: By excluding the lines not to submit the desired lines do not have to
be contiguous.

## INSTALLATION

Copy the SUBPART member, which is the REXX exec, into a library in your
SYSEXEC, or SYSPROC, allocations.
