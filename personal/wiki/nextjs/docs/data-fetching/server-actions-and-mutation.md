# Server Actions and Mutations

## Convention

- 'use server'

## Behavior

- can be invoked by:
  - form's action
  - useEffect
  - button
  - third-party libs

## Examples

- Forms
  - Passing additional arguments using `bind()`
  - Pending state with useFormStatus()
- Non-form elements
  - Event handlers
    - To improve the user experience, we recommend using other React APIs like useOptimistic and useTransition
    - debouncing???
  - useEffect()
    - I'm having trouble with Button's onClick() and I have to use useEffect
- Error Handling
- Revalidating data

## Security

