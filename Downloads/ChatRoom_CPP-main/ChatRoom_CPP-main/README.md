# ChatRoom-CPP

## Overview
ChatRoom-CPP is a simple chat room application that allows multiple clients to connect to a server and exchange messages in real-time. The application is built using C++ and utilizes the Boost.Asio library for asynchronous networking.

## Project Structure
```
ChatRoom-CPP
├── src
│   ├── chatroom.cpp
│   └── client.cpp
├── include
│   ├── chatroom.hpp
│   └── message.hpp
├── CMakeLists.txt
├── .gitignore
└── README.md
```

## Files Description
- **src/chatroom.cpp**: Contains the implementation of the `Room` and `Session` classes, which manage participants and message delivery in a chat room.
- **src/client.cpp**: Implements the client-side functionality for connecting to the chat room server, handling asynchronous reading and sending of messages.
- **include/chatroom.hpp**: Declares the `Participant`, `Room`, and `Session` classes, defining the interface for participants and chat room management.
- **include/message.hpp**: Declares the `Message` class, which handles message encoding and decoding.
- **CMakeLists.txt**: Configuration file for CMake, specifying project details and dependencies.
- **.gitignore**: Specifies files and directories to be ignored by Git.
- **README.md**: Documentation for the project.

## Build Instructions
1. Clone the repository:
   ```
   git clone <repository-url>
   cd ChatRoom-CPP
   ```

2. Create a build directory:
   ```
   mkdir build
   cd build
   ```

3. Run CMake to configure the project:
   ```
   cmake ..
   ```

4. Build the project:
   ```
   cmake --build .
   ```

## Usage
1. Start the server:
   ```
   ./chatroom <port>
   ```

2. Connect a client:
   ```
   ./client <port>
   ```

3. Enter messages in the client console to send them to the chat room.

## Dependencies
This project requires the Boost.Asio library. Please ensure that it is installed on your system before building the project. You can install it using your package manager or by following the instructions on the [Boost website](https://www.boost.org/).

## License
This project is licensed under the MIT License. See the LICENSE file for more details.