# Pydantic

`Pydantic` Python package guidelines.

## `BaseModel`

- Use validation_alias and serialization_alias when internal names differ from API contract names

## ORMs

- Prefer APIModel.model_validate(orm_obj) over manual field-by-field mapping

## Input Hardening

- Normalize inputs at model boundary instead of within consumers of a loaded model
