# password-strength-checker
print("--------Password Strength Checker-------")

password = input("Enter Your Password: ")

length_ok = len(password) >= 8
has_upper = any(char.isupper() for char in password)
has_lower = any(char.islower() for char in password)
has_digit = any(char.isdigit() for char in password)
has_special = any(char in "!@#$%^&*" for char in password)

score = sum ([length_ok , has_upper , has_lower , has_digit , has_special])

if score == 5:
    strength = "Strong Password"

elif score >=3:
    strength = "Moderate Password"

else:
    strength = "Weak Password"

print("\n Password Strength: ", strength)
print("\n Details: ")

print("Length >= 8 Characters" if length_ok else "Too Short(Min 8 Characters)")
print("Contains Uppercase Letter" if has_upper else "No Uppercase Letter")
print("Contains Lowercase Letter" if has_lower else "No Lowercase Letter")
print("Contains Digit" if has_digit else "No Digit")
print("Contain Special Character" if has_special else "No Special Character")
