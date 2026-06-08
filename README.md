#include <stdio.h>

int main() {

    int foodChoice, quantity, paymentChoice;
    float price = 0, totalAmount, finalAmount;

    char upiId[30];
    long long cardNumber;
    int password;

    printf("===== FOOD PAYMENT SYSTEM =====\n");

    // Food Menu
    printf("\n----- FOOD MENU -----\n");
    printf("1. Burger      - Rs 120\n");
    printf("2. Pizza       - Rs 250\n");
    printf("3. Fried Rice  - Rs 180\n");
    printf("4. Sandwich    - Rs 100\n");
    printf("5. Cool Drink  - Rs 50\n");

    // Food Selection
    printf("\nSelect Food Item: ");
    scanf("%d", &foodChoice);

    switch(foodChoice) {

        case 1:
            price = 120;
            printf("You Selected Burger\n");
            break;

        case 2:
            price = 250;
            printf("You Selected Pizza\n");
            break;

        case 3:
            price = 180;
            printf("You Selected Fried Rice\n");
            break;

        case 4:
            price = 100;
            printf("You Selected Sandwich\n");
            break;

        case 5:
            price = 50;
            printf("You Selected Cool Drink\n");
            break;

        default:
            printf("Invalid Food Choice!\n");
            return 0;
    }

    // Quantity
    printf("Enter Quantity: ");
    scanf("%d", &quantity);

    totalAmount = price * quantity;

    // Payment Methods
    printf("\n----- PAYMENT METHODS -----\n");
    printf("1. UPI\n");
    printf("2. Credit Card\n");
    printf("3. Debit Card\n");
    printf("4. Cash\n");

    printf("\nSelect Payment Method: ");
    scanf("%d", &paymentChoice);

    switch(paymentChoice) {

        case 1:
            printf("\nEnter UPI ID: ");
            scanf("%s", upiId);

            printf("Enter UPI Password: ");
            scanf("%d", &password);

            finalAmount = totalAmount;

            printf("\nUPI Payment Successful!\n");
            break;

        case 2:
            printf("\nEnter Credit Card Number: ");
            scanf("%lld", &cardNumber);

            printf("Enter Card Password/PIN: ");
            scanf("%d", &password);

            finalAmount = totalAmount + (totalAmount * 0.02);

            printf("\nCredit Card Payment Successful!\n");
            break;

        case 3:
            printf("\nEnter Debit Card Number: ");
            scanf("%lld", &cardNumber);

            printf("Enter Card Password/PIN: ");
            scanf("%d", &password);

            finalAmount = totalAmount + (totalAmount * 0.01);

            printf("\nDebit Card Payment Successful!\n");
            break;

        case 4:
            printf("\nCash Payment Selected\n");

            finalAmount = totalAmount;
            break;

        default:
            printf("\nInvalid Payment Choice!\n");
            return 0;
    }

    // Final Bill
    printf("\n===== FINAL BILL =====\n");
    printf("Total Amount : Rs %.2f\n", totalAmount);
    printf("Final Amount : Rs %.2f\n", finalAmount);

    printf("\nOrder Placed Successfully!\n");

    return 0;
}
