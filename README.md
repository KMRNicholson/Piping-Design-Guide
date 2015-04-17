# Piping-Design-Guide
Piping guide built to help technologist lay out pipe with accurate and safe dimensions.
// Program:     Piping Design Guide
// Date:        03/30/2015
// By:          Kohdy Nicholson
//
//Purpose:      The purpose of this program is to practice coding with C++.
//              This program demonstrates great use of menu's, use of loops,
//              if statements, and user-defined functions.

//              Keep in mind. This is low-level programming using c++.

#include <iostream>

int cte_90 = 1.5;
float cte_45 = 0.625, ui_nps;

int nps_3(float ui_nps), get_pressclass(void), main_menu(void), pipe_spacing(float ui_nps), get_valve_type(void);

int main()
{
    int mm_choice, valve_type;
    // User enters NPS of piping system
    std::cout << "Please enter NPS of pipe: " << std::endl;
    std::cin >> ui_nps;

    //This if statement will determine which function to call,
    //which is determined by the input entered in by the user
    if(ui_nps == 3)
    {
        nps_3(ui_nps);
    }

    return 0;
}

//This function defines all the data for the user for NPS 3 pipe systems
int nps_3(float ui_nps)
{
    //We begin by defining two variables for the pressure class (pressclass)
    //and the main menu choice (mm_choice)
    int pressclass, mm_choice;

    //We assign the value returned by the pressure class function (get_pressclass)
    //and the main menu function (main_menu) to our variables defined within this scope
    pressclass = get_pressclass();
    mm_choice = main_menu();

    if (mm_choice == 1)
    {
        std::cout << "\n\n*** PIPING DATA ***" << std::endl;
        std::cout << "____________________" << std::endl;
        std::cout << "\nOutside Diameter: \t\t3.5in" << std::endl;
        std::cout << "Outside Radius: \t\t1.75in" << std::endl;

        std::cout << "\n*** FITTING DATA ***" << std::endl;
        std::cout << "____________________" << std::endl;
        std::cout << "\n90 LR Elbow:\t\t " << cte_90 * ui_nps << "in" << std::endl;
        std::cout << "45 LR Elbow:\t\t " << cte_45 * ui_nps << "in" << std::endl;
    }
    if (mm_choice == 2)
    {
        if (pressclass == 150)
        {
            std::cout << "\n\n*** FLANGE DATA ***" << std::endl;
            std::cout << "____________________" << std::endl;
            std::cout << "\nWeld Neck Raised Face: \t\t3.125in" << std::endl;
            std::cout << "Flange Diameter: \t\t7.5in" << std::endl;
            std::cout << "Flange Thickness: \t\t0.9375in" << std::endl;

            std::cout << "\n*** BOLTING DATA ***" << std::endl;
            std::cout << "____________________" << std::endl;
            std::cout << "\nNumber of Bolts: \t\t4" << std::endl;
            std::cout << "Bolt Diameter: \t\t\t0.625" << std::endl;
            std::cout << "Bolt Length: \tStud - \t\t3.5in" << std::endl;
            std::cout << "\t\tMachine - \t3in" << std::endl;
        }
        if (pressclass == 300)
        {
            std::cout << "\n\n*** FLANGE DATA ***" << std::endl;
            std::cout << "____________________" << std::endl;
            std::cout << "\nWeld Neck Raised Face: \t\t3.125in" << std::endl;
            std::cout << "Flange Diameter: \t\t8.25in" << std::endl;
            std::cout << "Flange Thickness: \t\t1.125in" << std::endl;

            std::cout << "\n*** BOLTING DATA ***" << std::endl;
            std::cout << "____________________" << std::endl;
            std::cout << "\nNumber of Bolts: \t\t8" << std::endl;
            std::cout << "Bolt Diameter: \t\t\t0.75" << std::endl;
            std::cout << "Bolt Length: \tStud - \t\t4.25in" << std::endl;
            std::cout << "\t\tMachine - \t3.5in" << std::endl;
        }
        if (pressclass == 600)
        {
            std::cout << "\n\n*** FLANGE DATA ***" << std::endl;
            std::cout << "____________________" << std::endl;
            std::cout << "\nWeld Neck Raised Face: \t\t3.5in" << std::endl;
            std::cout << "Flange Diameter: \t\t8.25in" << std::endl;
            std::cout << "Flange Thickness: \t\t1.25in" << std::endl;

            std::cout << "\n*** BOLTING DATA ***" << std::endl;
            std::cout << "____________________" << std::endl;
            std::cout << "\nNumber of Bolts: \t\t8" << std::endl;
            std::cout << "Bolt Diameter: \t\t\t0.75" << std::endl;
            std::cout << "Bolt Length: \tStud - \t\t5in" << std::endl;
        }
        if (pressclass == 900)
        {
            std::cout << "\n\n*** FLANGE DATA ***" << std::endl;
            std::cout << "____________________" << std::endl;
            std::cout << "\nWeld Neck Raised Face: \t\t4.25in" << std::endl;
            std::cout << "Flange Diameter: \t\t9.5in" << std::endl;
            std::cout << "Flange Thickness: \t\t1.5in" << std::endl;

            std::cout << "\n*** BOLTING DATA ***" << std::endl;
            std::cout << "____________________" << std::endl;
            std::cout << "\nNumber of Bolts: \t\t8" << std::endl;
            std::cout << "Bolt Diameter: \t\t\t0.875" << std::endl;
            std::cout << "Bolt Length: \tStud - \t\t5.75in" << std::endl;
        }
    }
    if (mm_choice == 3)
    {
        int valvetype;

        valvetype = get_valve_type();

        if (valvetype == 1)
        {
            if (pressclass == 150)
            {
                std::cout << "\n\n*** GATE VALVE DATA ***" << std::endl;
                std::cout << "____________________" << std::endl;
                std::cout << "\nButt-Weld Overall Length: \t\t11.125in" << std::endl;
                std::cout << "Flanged Overall Length: \t\t8in" << std::endl;
            }
            if (pressclass == 300)
            {
                std::cout << "\n\n*** GATE VALVE DATA ***" << std::endl;
                std::cout << "____________________" << std::endl;
                std::cout << "\nOverall Length: \t\t11.125in" << std::endl;
            }
            if (pressclass == 600)
            {
                std::cout << "\n\n*** GATE VALVE DATA ***" << std::endl;
                std::cout << "____________________" << std::endl;
                std::cout << "\nOverall Length: \t\t14in" << std::endl;
            }
            if (pressclass == 900)
            {
                std::cout << "\n\n*** GATE VALVE DATA ***" << std::endl;
                std::cout << "____________________" << std::endl;
                std::cout << "\nOverall Length: \t\t14in" << std::endl;
            }
        }
        if (valvetype == 2)
        {
            if (pressclass == 150)
            {
                std::cout << "\n\n*** BALL VALVE DATA ***" << std::endl;
                std::cout << "____________________" << std::endl;
                std::cout << "\nRegular Port Overall Length: \t\t8in" << std::endl;
                std::cout << "Full Port Overall Length: \t\t8in" << std::endl;
            }
            if (pressclass == 300)
            {
                std::cout << "\n\n*** BALL VALVE DATA ***" << std::endl;
                std::cout << "____________________" << std::endl;
                std::cout << "\nRegular Port Overall Length: \t\t11.125in" << std::endl;
                std::cout << "Full Port Overall Length: \t\t11.125in" << std::endl;
            }
            if (pressclass == 600)
            {
                std::cout << "\n\n*** BALL VALVE DATA ***" << std::endl;
                std::cout << "____________________" << std::endl;
                std::cout << "\nRegular Port Overall Length: \t\t14in" << std::endl;
                std::cout << "Full Port Overall Length: \t\t14in" << std::endl;
            }
            if (pressclass == 900)
            {
                std::cout << "\n\n*** BALL VALVE DATA ***" << std::endl;
                std::cout << "____________________" << std::endl;
                std::cout << "\nRegular Port Overall Length: \t\t14in" << std::endl;
                std::cout << "Full Port Overall Length: \t\t14in" << std::endl;
            }
        }
    }
    if (mm_choice == 4)
    {
        pipe_spacing(ui_nps);
    }
}

//This function gets the main menu choice from the user
int main_menu(void)
{
    int mm_choice;

    std::cout << "\nPlease select an option: " << std::endl;
    std::cout << "1 - Pipe/fitting data" << std::endl;
    std::cout << "2 - Flange/bolting data" << std::endl;
    std::cout << "3 - Valve data" << std::endl;
    std::cout << "4 - Centerline spacing" << std::endl;

    std::cin >> mm_choice;

    return mm_choice;
}

//This function gets the pressure class of the piping system
int get_pressclass(void)
{
    int pressclass;

    std::cout << "\nPlease enter pressure class: " << std::endl;
    std::cin >> pressclass;

    return pressclass;
}

//This function gets the valve type for the valve data
int get_valve_type(void)
{
    int valvetype;

    std::cout << "\nPlease select an option: " << std::endl;
    std::cout << "1 - Gate" << std::endl;
    std::cout << "2 - Ball" << std::endl;

    std::cin >> valvetype;

    return valvetype;
}

//This function will obtain information on pipe spacing based on
//the pipe size it will be beside
int pipe_spacing(float ui_nps)
{
    int choice = 0, ui_nps2, ui_ins1, ui_ins2;

    std::cout << "\nPlease enter NPS of other pipe: " << std::endl;
    std::cin >> ui_nps2;

    std::cout << "\nDoes either pipe have insulation?" << std::endl;
    std::cout << "1 - Yes" << std::endl;
    std::cout << "2 - No" << std::endl;

    std::cin >> choice;

    if (choice == 1)
    {
        std::cout << "Do both pipes have insulation?" << std::endl;
        std::cout << "1 - Yes" << std::endl;
        std::cout << "2 - No" << std::endl;

        std::cin >> choice;

        if (choice == 1)
        {
            std::cout << "Please enter the insulation of both pipes: " << std::endl;
            std::cin >> ui_ins1, ui_ins2;


        }
    }
}
