#include <iostream>
#include <string>
#include <vector>
#include <ctime>
#include <cstdlib>

class Farm {
public:
    Farm() : money(100), crops(0), chickenCount(0), cowCount(0), level(1), experience(0) {
        srand(time(0));
    }

    void plantCrop() {
        if (money >= 10) {
            crops++;
            money -= 10;
            std::cout << "You planted a crop! Now you've got " << crops << " crops growing like wild! 🌾\n";
        } else {
            std::cout << "You're too broke to plant a crop! 😂 Go make some money, farmer!\n";
        }
    }

    void harvestCrop() {
        if (crops > 0) {
            int bonus = (rand() % 10) + 1;
            money += (20 + bonus);
            crops--;
            experience += 10;
            std::cout << "You harvested a crop! Cha Ching! 💸 You earned $" << (20 + bonus) << " and 10XP!\n";
            checkLevelUp();
        } else {
            std::cout << "No crops to harvest! Your farming skills are WEAK 😂\n";
        }
    }

    void buyChicken() {
        if (money >= 50) {
            chickenCount++;
            money -= 50;
            std::cout << "You bought a chicken! 🐓 Now you've got " << chickenCount << " chickens clucking around!\n";
        } else {
            std::cout << "You're too broke to buy a chicken! 😂\n";
        }
    }

    void buyCow() {
        if (money >= 200) {
            cowCount++;
            money -= 200;
            std::cout << "You bought a cow! 🐮 Now you've got " << cowCount << " cows mooooving around!\n";
        } else {
            std::cout << "You're too broke to buy a cow! 😂\n";
        }
    }

    void chickenSays() {
        if (chickenCount > 0) {
            std::cout << "Your chicken says: BOCK BOCK! 🐓\n";
        } else {
            std::cout << "You don't have a chicken to talk to you! 😂\n";
        }
    }

    void cowSays() {
        if (cowCount > 0) {
            std::cout << "Your cow says: MOOOOO! 🐮\n";
        } else {
            std::cout << "You don't have a cow to talk to you! 😂\n";
        }
    }

    void checkLevelUp() {
        if (experience >= 100) {
            level++;
            experience = 0;
            std::cout << "LEVEL UP! 🎉 You're now level " << level << "! You got a 10% discount on all animals!\n";
        }
    }

    void market() {
        std::cout << "Welcome to the market! 🎉\n";
        std::cout << "1. Buy chicken ($50)\n2. Buy cow ($200)\n3. Sell crops ($30 each)\n4. Exit market\n";
        int choice;
        std::cin >> choice;

        switch (choice) {
        case 1:
            buyChicken();
            break;
        case 2:
            buyCow();
            break;
        case 3:
            if (crops > 0) {
                money += (crops * 30);
                std::cout << "You sold " << crops << " crops for $" << (crops * 30) << "!\n";
                crops = 0;
            } else {
                std::cout << "No crops to sell! 😂\n";
            }
            break;
        case 4:
            std::cout << "Thanks for visiting the market! 🎉\n";
            break;
        default:
            std::cout << "Invalid choice! You're a terrible trader 😂\n";
        }
    }

    void status() {
        std::cout << "Your farm status:\n";
        std::cout << "Money: $" << money << "\n";
        std::cout << "Crops: " << crops << "\n";
        std::cout << "Chickens: " << chickenCount << "\n";
        std::cout << "Cows: " << cowCount << "\n";
        std::cout << "Level: " << level << "\n";
        std::cout << "Experience: " << experience << "/100\n";
    }

private:
    int money;
    int crops;
    int chickenCount;
    int cowCount;
    int level;
    int experience;
};

int main() {
    Farm myFarm;
    int choice;

    while (true) {
        std::cout << "1. Plant crop\n2. Harvest crop\n3. Talk to chicken\n4. Talk to cow\n5. Market\n6. Status\n7. Exit\n";
        std::cin >> choice;

        switch (choice) {
        case 1:
            myFarm.plantCrop();
            break;
        case 2:
            myFarm.harvestCrop();
            break;
        case 3:
            myFarm.chickenSays();
            break;
        case 4:
            myFarm.cowSays();
            break;
        case 5:
            myFarm.market();
            break;
        case 6:
            myFarm.status();
            break;
        case 7:
            std::cout << "Thanks for farming with us! 🎉\n";
            return 0;
        default:
            std::cout << "Invalid choice! You're a terrible farmer 😂\n";
        }
    }

    return 0;
}
#include <iostream>
#include <string>
#include <vector>
#include <ctime>
#include <cstdlib>

class Farm {
public:
    Farm() : money(100), crops(0), chickenCount(0), cowCount(0), level(1), experience(0) {
        srand(time(0));
    }

    void plantCrop() {
        if (money >= 10) {
            crops++;
            money -= 10;
            std::cout << "You planted a crop! Now you've got " << crops << " crops growing like wild! 🌾\n";
        } else {
            std::cout << "You're too broke to plant a crop! 😂 Go make some money, farmer!\n";
        }
    }

    void harvestCrop() {
        if (crops > 0) {
            int bonus = (rand() % 10) + 1;
            money += (20 + bonus);
            crops--;
            experience += 10;
            std::cout << "You harvested a crop! Cha Ching! 💸 You earned $" << (20 + bonus) << " and 10XP!\n";
            checkLevelUp();
        } else {
            std::cout << "No crops to harvest! Your farming skills are WEAK 😂\n";
        }
    }

    void buyChicken() {
        if (money >= 50) {
            chickenCount++;
            money -= 50;
            std::cout << "You bought a chicken! 🐓 Now you've got " << chickenCount << " chickens clucking around!\n";
        } else {
            std::cout << "You're too broke to buy a chicken! 😂\n";
        }
    }

    void buyCow() {
        if (money >= 200) {
            cowCount++;
            money -= 200;
            std::cout << "You bought a cow! 🐮 Now you've got " << cowCount << " cows mooooving around!\n";
        } else {
            std::cout << "You're too broke to buy a cow! 😂\n";
        }
    }

    void chickenSays() {
        if (chickenCount > 0) {
            std::cout << "Your chicken says: BOCK BOCK! 🐓\n";
        } else {
            std::cout << "You don't have a chicken to talk to you! 😂\n";
        }
    }

    void cowSays() {
        if (cowCount > 0) {
            std::cout << "Your cow says: MOOOOO! 🐮\n";
        } else {
            std::cout << "You don't have a cow to talk to you! 😂\n";
        }
    }

    void checkLevelUp() {
        if (experience >= 100) {
            level++;
            experience = 0;
            std::cout << "LEVEL UP! 🎉 You're now level " << level << "! You got a 10% discount on all animals!\n";
        }
    }

    void market() {
        std::cout << "Welcome to the market! 🎉\n";
        std::cout << "1. Buy chicken ($50)\n2. Buy cow ($200)\n3. Sell crops ($30 each)\n4. Exit market\n";
        int choice;
        std::cin >> choice;

        switch (choice) {
        case 1:
            buyChicken();
            break;
        case 2:
            buyCow();
            break;
        case 3:
            if (crops > 0) {
                money += (crops * 30);
                std::cout << "You sold " << crops << " crops for $" << (crops * 30) << "!\n";
                crops = 0;
            } else {
                std::cout << "No crops to sell! 😂\n";
            }
            break;
        case 4:
            std::cout << "Thanks for visiting the market! 🎉\n";
            break;
        default:
            std::cout << "Invalid choice! You're a terrible trader 😂\n";
        }
    }

    void status() {
        std::cout << "Your farm status:\n";
        std::cout << "Money: $" << money << "\n";
        std::cout << "Crops: " << crops << "\n";
        std::cout << "Chickens: " << chickenCount << "\n";
        std::cout << "Cows: " << cowCount << "\n";
        std::cout << "Level: " << level << "\n";
        std::cout << "Experience: " << experience << "/100\n";
    }

private:
    int money;
    int crops;
    int chickenCount;
    int cowCount;
    int level;
    int experience;
};

int main() {
    Farm myFarm;
    int choice;

    while (true) {
        std::cout << "1. Plant crop\n2. Harvest crop\n3. Talk to chicken\n4. Talk to cow\n5. Market\n6. Status\n7. Exit\n";
        std::cin >> choice;

        switch (choice) {
        case 1:
            myFarm.plantCrop();
            break;
        case 2:
            myFarm.harvestCrop();
            break;
        case 3:
            myFarm.chickenSays();
            break;
        case 4:
            myFarm.cowSays();
            break;
        case 5:
            myFarm.market();
            break;
        case 6:
            myFarm.status();
            break;
        case 7:
            std::cout << "Thanks for farming with us! 🎉\n";
            return 0;
        default:
            std::cout << "Invalid choice! You're a terrible farmer 😂\n";
        }
    }

    return 0;
}
