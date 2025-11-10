#
# Copyright (C) 2020 The Android Open Source Project
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

cmake_minimum_required(VERSION 3.6)
project(simdjson LANGUAGES CXX)

file(GLOB src_files ../include/simdjson/simdjson.cpp)

add_library(simdjson SHARED ${src_files})
target_include_directories(simdjson PUBLIC include)

target_link_options(simdjson PRIVATE -Wl,-z,max-page-size=16384)

set_target_properties(simdjson PROPERTIES LINKER_LANGUAGE CXX)
