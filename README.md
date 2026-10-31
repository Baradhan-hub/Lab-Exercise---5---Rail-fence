# Lab-Exercise---5---Rail-fence
## Aim
To develop a simple C program to implement Rail Fence Cipher.
## Procedure 
1. Design of Rail Fence Cipher algorithm.
2. Implementation using C or Python code.
3. Testing algorithm with different key values.
4. In the Rail Fence Cipher, the plaintext is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail.
5. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

## PROGRAM:
```
def rail_fence_encrypt(text, rails):
    if rails == 1:
        return text

    # Create the 2D matrix filled with '\n'
    fence = [['\n' for _ in range(len(text))] for _ in range(rails)]

    row = 0
    direction = 1  # 1 for downward, -1 for upward

    # Place characters in the zig-zag pattern
    for col, char in enumerate(text):
        fence[row][col] = char

        if row == 0:
            direction = 1
        elif row == rails - 1:
            direction = -1

        row += direction

    # Read row by row to construct ciphertext
    encrypted_text = ""
    for row in fence:
        for char in row:
            if char != '\n':
                encrypted_text += char

    return encrypted_text


message = input("Enter the plaintext: ")
rails = int(input("Enter the number of rails: "))

ciphertext = rail_fence_encrypt(message, rails)

print("Plaintext:", message)
print("Encrypted text:", ciphertext)
```
## output
<img width="1317" height="167" alt="image" src="https://github.com/user-attachments/assets/7f9f970b-4e38-479a-8625-40ccfa143245" />

## Result
The program executed successfully.


