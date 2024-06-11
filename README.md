ANGGOTA KELOMPOK :

1. IMAM RIFAI (2317051093)
2. ANINDIA GITA CAHYANI (2317051104)
3. ZAHRA AGRIPHINNA (2357051022)

#include <iostream>
#include <map>
#include <fstream>
using namespace std;

struct User {
    string username;
    string password;
};

class Cinema {
private:
    map<string, string> users;

public:
    Cinema() {
        loadUsers();
    }

    void loadUsers() {
        ifstream infile("users.txt");
        string username, password;
        while (infile >> username >> password) {
            users[username] = password;
        }
        infile.close();
    }

    void saveUser(const string &username, const string &password) {
        ofstream outfile("users.txt", ios::app);
        outfile << username << " " << password << endl;
        outfile.close();
    }

    bool registerUser(const string &username, const string &password) {
        if (users.find(username) != users.end()) {
            return false;
        }
        users[username] = password;
        saveUser(username, password);
        return true;
    }

    bool loginUser(const string &username, const string &password) {
        return users.find(username) != users.end() && users[username] == password;
    }
};

int main () {
    return 0;
}
