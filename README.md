import random
import string

def generate_password(length):
    # Define character sets for password complexity
    lowercase = string.ascii_lowercase
    uppercase = string.ascii_uppercase
    digits = string.digits
    symbols = string.punctuation
    
    # Combine all character sets
    all_characters = lowercase + uppercase + digits + symbols
    
    # Generate password
    password = ''.join(random.choice(all_characters) for _ in range(length))
    return password

def main():
    try:
        # Prompt user for password length
        length = int(input("Enter the desired password length: "))
        
        # Validate input
        if length <= 0:
            print("Please enter a positive number.")
            return
            
        # Generate and display password
        password = generate_password(length)
        print(f"Generated Password: {password}")
        
    except ValueError:
        print("Please enter a valid number.")

if __name__ == "__main__":
    main()
