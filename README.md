# ValidationEmail

- Type 1
```java
public static boolean isEmailValid(String email) {
    boolean isValid = false;

    String expression = "^[\\w\\.-]+@([\\w\\-]+\\.)+[A-Z]{2,4}$";
    CharSequence inputStr = email;

    Pattern pattern = Pattern.compile(expression, Pattern.CASE_INSENSITIVE);
    Matcher matcher = pattern.matcher(inputStr);
    if (matcher.matches()) {
        isValid = true;
    }
    return isValid;
}
```

- Type 2
```java
public static boolean isValidEmail(CharSequence target) {
    return (!TextUtils.isEmpty(target) && Patterns.EMAIL_ADDRESS.matcher(target).matches());
}
```

```kotlin
fun CharSequence?.isValidEmail() = !isNullOrEmpty() && Patterns.EMAIL_ADDRESS.matcher(this).matches()
```

---

```
Copyright 2020 M. Fadli Zein
```
