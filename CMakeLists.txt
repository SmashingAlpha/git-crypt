cmake_minimum_required(VERSION 3.28)

project(git-crypt LANGUAGES CXX)

find_package(OpenSSL REQUIRED)

add_executable(git-crypt)
set_property(TARGET git-crypt PROPERTY CXX_STANDARD 11)
target_sources(git-crypt PRIVATE
git-crypt.cpp
commands.cpp
crypto.cpp
gpg.cpp
key.cpp
util.cpp 
parse_options.cpp
coprocess.cpp 
fhstream.cpp
crypto-openssl-10.cpp 
crypto-openssl-11.cpp
)
target_link_libraries(git-crypt PRIVATE openssl::openssl)
target_include_directories(git-crypt PRIVATE openssl::openssl)
