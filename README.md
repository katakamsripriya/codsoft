#Task 1
#include <stdio.h>
#include <string.h>

#define NUM_USERS 3
#define NUM_ITEMS 3

// Define a struct to represent a user
typedef struct {
    char name[50];
    int preferences[NUM_ITEMS];
} User;

// Function prototypes
void initialize_users(User users[NUM_USERS]);
void recommend_items(User users[NUM_USERS], int user_index);

int main() {
    User users[NUM_USERS];
    initialize_users(users);

    // Assuming user 0 wants a recommendation
    int user_index = 0;
    recommend_items(users, user_index);

    return 0;
}

// Initialize user data
void initialize_users(User users[NUM_USERS]) {
    strcpy(users[0].name, "User1");
    users[0].preferences[0] = 5;
    users[0].preferences[1] = 3;
    users[0].preferences[2] = 1;

    strcpy(users[1].name, "User2");
    users[1].preferences[0] = 2;
    users[1].preferences[1] = 4;
    users[1].preferences[2] = 5;

    strcpy(users[2].name, "User3");
    users[2].preferences[0] = 4;
    users[2].preferences[1] = 1;
    users[2].preferences[2] = 3;
}

// Recommend items to the user based on their preferences
void recommend_items(User users[NUM_USERS], int user_index) {
    printf("Recommendations for %s:\n", users[user_index].name);

    for (int item = 0; item < NUM_ITEMS; item++) {
        // Simple content-based recommendation: suggest items with high preferences
        if (users[user_index].preferences[item] >= 4) {
            printf("Item %d\n", item + 1);
        }
    }
}
