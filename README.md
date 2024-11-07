# Prodigy-internship
A comprehensive cybersecurity internship repository showcasing hands-on projects and tools used in real-world SOC environments. Includes examples in ethical hacking, threat analysis, and network defense strategies. 

#Create a python program that can encrpt and decrypt text using the caesar cipher algorithm.allow users to input a msg and a shift value to perform encryption and decryption
def caesar_cipher(text, shift, mode='encrypt'):
    result = ""
    for char in text:
        if char.isalpha():  # Check if character is a letter
            shift_base = ord('A') if char.isupper() else ord('a')
            shift_direction = shift if mode == 'encrypt' else -shift
            result += chr((ord(char) - shift_base + shift_direction) % 26 + shift_base)
        else:
            result += char  # Non-alphabetical characters remain unchanged
    return result

# User input
message = input("Enter the message: ")
shift_value = int(input("Enter the shift value: "))

# Encrypt the message
encrypted_message = caesar_cipher(message, shift_value, mode='encrypt')
print(f"Encrypted Message: {encrypted_message}")

# Decrypt the message
decrypted_message = caesar_cipher(encrypted_message, shift_value, mode='decrypt')
print(f"Decrypted Message: {decrypted_message}")
