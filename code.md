# Inheritance_Assignment_R156449E_DAIT17
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */

/* 
 * File:   main.cpp
 * Author: tina
 *
 * Created on September 29, 2016, 10:02 PM
 */

#include <cstdlib>
#include <iostream>

using namespace std;

/*
 * 
 */
class Student {
    string RegNum;
    string Program;
    string name;
    int age;
public:

    Students(string thisRegNum, string thisName, int thisAge) {
        RegNum = thisRegNum;
        name = thisName;
        age = thisAge;

    }

    void setStudent(string thisRegNum, string thisName, int thisAge, string pro) {
        RegNum = thisRegNum;
        name = thisName;
        age = thisAge;
        Program = pro;

    };
    //Making Sure If Inheritance Was Properly Implemented

    void confirmStudent() {
        cout << "RegNumber=>" << RegNum << "\nName=>" << name << "\nAge=>" << age << "\nProgram" << Program;
    }

};

class SotStudent : public Student {
    string level;
    int coreCourseMark;
    int otherAverageMarks;
    string program;
    string areaOfSpecialisation;
    int numberOfBussinessModules;
public:
    void fieldAllocation();

    void setSot(string thisLev, int thisCourseMark, int thisAvg, string thisSpec, int N_O_B_M) {
        level = thisLev;
        coreCourseMark = thisCourseMark;
        otherAverageMarks = thisAvg;

        areaOfSpecialisation = thisSpec;
        numberOfBussinessModules = N_O_B_M;
    }
    //Making Sure If Inheritance Was Properly Implemented

    void confirmSot() {
        cout << "\nLevel=>" << level << "\nCourse Mark=>" << coreCourseMark << "\nAverage of other modules=>" << otherAverageMarks << "\nSpecialising in=>" << areaOfSpecialisation << "\nNumber of business modules" << numberOfBussinessModules;
    }


};

class LawStudent : public Student {
    int Semester;
    int year;
public:

    void setLaw(int sem, int yr) {
        Semester = sem;
        year = yr;
    }
    LawStudent();
};

class Dait : public SotStudent {
    int projects;

public:
    void course();

    void setDait(int proj) {
        projects = proj;
    }
    //Making Sure If Inheritance Was Properly Implemented

    void confirmDait() {
        cout << "\nNumber of projects=>" << projects;
    }

};

class CAIT : public SotStudent {
    int foundationCourseAvg;
public:
    void course();

    void setCait(int avg) {
        foundationCourseAvg = avg;
    }

    CAIT() {
        cout << "We are doing Certificate" << endl;
    };
};

class Software : public Dait {
    int numberOfLanguages;
public:

    void setSoftware(int thisLanguage) {
        numberOfLanguages = thisLanguage;
    }

    Software(string Regn, string nme, int ag, string progr, string lvl, int CoursMark, int thisAv, string spe, int bus, int projec, int lang) {
        setStudent(Regn, nme, ag, progr);
        setSot(lvl, CoursMark, thisAv, spe, bus);
        setDait(projec);
        setSoftware(lang);
    }
    //Making Sure If Inheritance Was Properly Implemented

    void confirmSoftware() {
        cout << "\nNumber of Languages=>" << numberOfLanguages;
    }

    void Programme() {
        cout << "working on a Parking System" << endl;
    }

};

class Hardware : public Dait {
    int damagedPCs;
public:

    void setPC(int thisDam) {
        damagedPCs = thisDam;
    }

    Hardware(string Regn, string nme, int ag, string progr, string lvl, int CoursMark, int thisAv, string spe, int bus, int projec, int dam) {
        setStudent(Regn, nme, ag, progr);
        setSot(lvl, CoursMark, thisAv, spe, bus);
        setDait(projec);
        setPC(dam);
    }
    //Making Sure If Inheritance Was Properly Implemented

    void confirmHardware() {
        cout << "\nNumber of Damages Pcs=>" << damagedPCs;
    }

    void Fix() {
        cout << "Let us do our work" << endl;

    }
};

int main(int argc, char** argv) {

    Software student1("R156449E", "Tinashe", 40, "I.T", "DIPLOMA", 80, 90, "Software", 4, 2, 6);
    Hardware student2("R153249E", "Nash", 10, "I.T", "DIPLOMA", 80, 90, "Hardware", 4, 2, 6);

    student1.confirmStudent();
    student1.confirmSot();
    student1.confirmDait();
    student1.confirmSoftware();
    cout << "\n\n";

    student2.confirmStudent();
    student2.confirmSot();
    student2.confirmDait();
    student2.confirmHardware();
    return 0;
}
