# Neolurk
api for neolurk.org censored free wiki
# main
```cpp
#include "Neolurk.h"
#include <iostream>

int main() {
   Neolurk api;

    auto search = api.search("q").then([](json::value result) {
        std::cout << "Search results: " << result.serialize() << std::endl;
    });
    search.wait();
    
    return 0;
}
```

# Launch (your script)
```
g++ -std=c++11 -o main main.cpp -lcpprest -lssl -lcrypto -lpthread -lboost_system -lboost_chrono -lboost_thread
./main
```
