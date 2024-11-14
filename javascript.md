### Javascript

## Function

# test

```javascript
<input
  {...props}
  id={id}
  ref={ref}
  disabled={disabled}
  readOnly={readOnly}
  defaultValue={defaultValue}
  placeholder={placeholder}
  className={clsx(
    props.className,
    styles.input,
    error && styles.errorInput,
    disabled && styles.disabled.input,
    readOnly && styles.readOnly
  )}
/>
```
