# Repository Guidelines

## Project Structure

This repository collects IDL (`.pro`) routines by subject. `atomic/`, `molecular/`, and `partition_functions/` contain spectroscopy data utilities and their data files. `carlson_quadrature/`, `legendre_polynomials/`, `numerical_methods/`, `radtrans_basics/`, and `splines_and_interpolations/` contain numerical and radiative-transfer routines. Data tables and example procedures are kept beside the routines that use them; several directories have a short README.

## Build, Test, and Development

There is no repository-wide build system, test suite, or linter. With IDL installed, add the directory containing the routine to IDL's procedure search path, then compile or call the routine in the interpreter. Use examples such as `partition_functions/pf_example.pro` to exercise related functions. Examples may open plots, write image files, or stop the interpreter, so review their effects before running them in batch workflows.

## Coding Style

Use lowercase `snake_case` for routine names and matching `.pro` filenames, following the existing library layout. IDL keywords and built-in procedures are commonly uppercase. Match the surrounding file's indentation and formatting; conventions vary across this collection. For public routines, keep the IDL comment header (`;`) with purpose, calling sequence, inputs, outputs, and dependencies where relevant.

## Testing and Data Configuration

When changing a routine, run it in IDL with a representative input and compare its result with the documented example or expected data behavior. No automated coverage requirement is configured. Data-dependent routines may include `molecular/molecules_path.pro` or `partition_functions/pf_path.pro`, which point to installation-specific directories. Set these paths to the local data directory before running those routines, and keep machine-specific path changes out of contributions.

## Commits and Pull Requests

Git history uses short descriptive subjects but has no consistent formal convention. Prefer a concise imperative subject, for example `Update splinecoeff.pro`. Pull requests should explain the purpose and affected routines or data, list manual checks and any required local configuration, and link a related issue when one exists.
