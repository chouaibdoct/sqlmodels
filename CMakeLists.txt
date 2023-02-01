cmake_minimum_required(VERSION 3.5)

project(lecact_intern LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)		

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)


find_package(Qt6 COMPONENTS Core Sql REQUIRED)



# target_include_directories(utils SYSTEM INTERFACE ./verdigris)
# target_include_directories(utils INTERFACE  .)



qt_add_library(sqlmodel
  SHARED
#  qsqlquerymodel.cpp qsqlquerymodel.h qsqlquerymodel_p.h
qsqltablemodel.cpp qsqltablemodel.h qsqltablemodel_p.h
#qsqlrelationaldelegate.cpp qsqlrelationaldelegate.h
#qsqlrelationaltablemodel.cpp qsqlrelationaltablemodel.h

)

target_include_directories(sqlmodel SYSTEM INTERFACE ./verdigris)
target_include_directories(sqlmodel INTERFACE  .)
target_link_libraries(sqlmodel   Qt::Core Qt::CorePrivate Qt::Sql Qt::SqlPrivate)


