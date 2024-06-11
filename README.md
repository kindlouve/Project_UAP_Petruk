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
