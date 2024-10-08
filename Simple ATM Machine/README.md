# ATM State Machine Diagram
The diagram models the sequence of states and actions that an ATM machine undergoes during a typical user session. It captures how the system transitions between states such as card insertion, authentication, cash withdrawal, balance checking, and other services. Each state is triggered by user inputs or system conditions, and the flow continues until the card is ejected.

## Key Components of the ATM State Machine

1. **Idle**: The initial state of the ATM where the machine is waiting for user interaction. 
    - Transition: Insert card.

2. **Card Inserted**: The state where the ATM detects the card and prompts the user to authenticate.
    - Transition: Authenticate card.

3. **Authenticated**: The ATM has successfully verified the card and the user can now access the main menu.
    - Transition: Access main menu.

4. **Main Menu**: The user is presented with options such as card registration, balance check, withdrawal, or PIN change.
    - Transitions: 
        - Select card registration.
        - Select withdrawal.
        - Select balance check.
        - Select PIN change.

5. **Card Registration Process**:
    - **Card Registration Requested**: The user selects card registration and enters their required details.
    - **Reading Required Details**: The ATM reads the user’s entered details.
    - **OTP Sent**: The system sends an OTP (One-Time Password) for verification.
    - **Sending Confirmation Message**: Once the correct OTP is entered, a confirmation message is sent.

6. **Withdrawal Process**:
    - **Withdraw Process Initiates**: The user selects the withdrawal option.
    - **Reading Amount**: The system reads the amount the user wishes to withdraw.
    - **Reading PIN**: The system requests the user’s PIN for authentication.
    - **Dispensing Cash**: If the entered PIN is correct and the amount is valid, the ATM dispenses cash.
    - **Generating Slip & SMS**: The system generates a slip and sends an SMS confirmation of the transaction.

7. **Balance Check Process**:
    - **Balance Check Process Initiates**: The user selects the balance check option.
    - **Reading PIN**: The system requests the user’s PIN for authentication.
    - **Displaying Balance**: The system displays the account balance if the PIN is correct.

8. **Change of PIN Process**:
    - **Change of PIN Requested**: The user selects the option to change their PIN.
    - **Reading Old PIN**: The system requests the old PIN.
    - **Reading New PIN**: If the old PIN is correct, the system reads the new PIN and confirms the change.

9. **Ejecting Card**: At the end of all processes, the ATM ejects the card, returning to the idle state.

## Key Features of the Diagram

- **Decision Points**: The diagram has decision points (diamonds) where a process can proceed differently based on the input, such as correct or incorrect PIN entries.
- **Parallel Processes**: The ATM can handle multiple types of requests like withdrawals, PIN changes, or balance checks simultaneously after the user reaches the main menu.
- **Error Handling**: Incorrect inputs like wrong PIN or OTP lead to alternate flows such as re-entering details or ending the session.


