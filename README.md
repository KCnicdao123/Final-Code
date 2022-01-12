# Final-Code
#include <iostream>
#include <string>
using namespace std;

double change(double payment, double price) {
	if (payment < price) {
		cout << "I'm sorry, but you do not have enough for that drink.\n";
	}
	else {
		double userChange = payment - price;
		cout << "Payment confirmed. Your change is " << userChange << " AED.";
	}
	return payment, price;
}

void userSugar(char ans) {
	if (ans == 'Y' || ans == 'y') {
		cout << "Adding sugar.\n";
	}
	else {
		cout << "Skipping sugar.\n";
	}
}

int price(int drink) {
	switch (drink) {
	case 1:
		cout << "That would be for 3.00 AED.";
		break;
	case 2:
		cout << "That would be for 2.00 AED";
		break;
	case 3:
		cout << "That would be for 1.00 AED.";
		break;
	}
	char sugar;
	do {
		cout << "\nWould you like some sugar ? (Y / N)\n";
		cin >> sugar;
	} while (sugar != 'y' && sugar != 'Y' && sugar != 'n' && sugar != 'N');
	userSugar(sugar);
	return drink;
} 

char drink(char type) {
	if (type == 'c' || type == 'C') {
		int coffee;
		do {
			cin.clear();
			cin.ignore(10000, '\n');
			cout << "What kind of coffee would you like? (Pick from 1 - 3)\n";
			cin >> coffee;
		} while (coffee < 1 || coffee > 3);
		price(coffee);
		cout << "How much would you like to pay for that?\n";
		double userPay;
		cin >> userPay;
		while (coffee == 1) {
			double Price = 3;
			change(userPay, Price);
			break;
		}while (coffee == 2) {
			double Price2 = 2;
			change(userPay, Price2);
			break;
		}while (coffee == 3) {
			double Price3 = 1;
			change(userPay, Price3);
			break;
		}
	}else {
		int tea;
		do {
			cin.clear();
			cin.ignore(10000, '\n');
			cout << "What kind of tea would you like? (Pick from 1 - 3)\n";
			cin >> tea;
		} while (tea < 1 || tea > 3);
		price(tea);
		cout << "How much would you like to pay for that?\n";
		double userPay;
		cin >> userPay;
		while (tea == 1) {
			double Price = 3;
			change(userPay, Price);
			break;
		}while (tea == 2) {
			double Price2 = 2;
			change(userPay, Price2);
			break;
		}while (tea == 3) {
			double Price3 = 1;
			change(userPay, Price3);
			break;
		}
	}
	return type;
}

int main() {
	string menu[4][4] = {
		{"     Coffee", "      Price (AED)", "     Tea", "     Price (AED)"},
		{"1. Ice Coffee", "       3", "       1. Ice Tea", "        3"},
		{"2. Milk Coffee", "      2", "       2. Milk Tea", "       2"},
		{"3. Black Coffee", "     1", "       3. Black Tea", "      1"}
	};
	for (int x = 0; x < 4; x++) {
		for (int y = 0; y < 4; y++) {
			cout << menu[x][y];
		}cout << endl;
	}
	char userDrink;
	do {
		cout << "\nWhat drink would you like? (C for coffee or T for tea?)\n";
		cin >> userDrink;
	} while (userDrink != 'C' && userDrink != 'c' && userDrink != 'T' && userDrink != 't');
	drink(userDrink);
	cout << "\nThank you and have a nice day!";
}
