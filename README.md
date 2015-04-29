// Program:     Piping Design Guide
// Date:        03/30/2015
// By:          Kohdy Nicholson
//
//Purpose:      The purpose of this program is to practice coding with C++.
//              This program demonstrates great use of menu's, use of loops,
//              if statements, and user-defined functions.

//              Keep in mind. This is low-level programming using c++.

//              Change log:
//              * April 24, 2015    - Added a change log!
//                                  - Adding menu loops and "return to previous"
//                                    options to menus.
//                                  - Cleaned up format.
//              * April 28, 2015    - Added the std namespace variables and cleaned
//                                    up all I/O statements.

#include <iostream>

using std::cout;
using std::endl;
using std::cin;

//Defining objects and user-defined functions
int cte_90 = 1.5;

float cte_45 = 0.625, ui_nps = 0, ui_nps2, ui_ins1, ui_ins2;

int nps_3(float ui_nps), get_pressclass(void), main_menu(void), get_valve_type(void);

float pipe_spacing(float ui_nps);
float pipe_space1(float ui_nps, float ui_nps2, float ui_ins1, float ui_ins2);
float pipe_space2(float ui_nps, float ui_nps2, float ui_ins1, float ui_ins2);

//Main function used to calculate user-defined functions based on NPS size
int main()
{
    int mm_choice, valve_type;

    // User enters NPS of piping system
    while (ui_nps = 100)
    {

    mm_choice = 0;
    while ((ui_nps > 24) || (ui_nps < 2))
    {
        cout << "\nPlease enter NPS of pipe (2.5\" to 24\"): " << endl;
        cin >> ui_nps;
    }

    //This if statement will determine which function to call,
    //which is determined by the input entered in by the user
    if(ui_nps == 3)
    {
        nps_3(ui_nps);
    }
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
    while (mm_choice != 5)
    {
    pressclass = get_pressclass();
    mm_choice = main_menu();

    if (mm_choice == 1)
    {
        cout << "\n\n*** PIPING DATA ***"
         "\n____________________"
         "\n\nOutside Diameter: \t\t3.5\""
         "\nOutside Radius: \t\t1.75\""                       << endl;

        cout << "\n*** FITTING DATA ***"
         "\n____________________"
         "\n\n90 LR Elbow:\t\t " << cte_90 * ui_nps << "\""
         "\n45 LR Elbow:\t\t " << cte_45 * ui_nps << "\""     << endl;
        mm_choice = 5;
    }
    if (mm_choice == 2)
    {
        if (pressclass == 1)
        {
            cout << "\n\n*** FLANGE DATA ***"
             "\n____________________"
             "\n\nWeld Neck Raised Face: \t\t3.125\""
             "\nFlange Diameter: \t\t7.5\""
             "\nFlange Thickness: \t\t0.9375\""               << endl;

            cout << "\n*** BOLTING DATA ***"
             "\n____________________"
             "\n\nNumber of Bolts: \t\t4"
             "\nBolt Diameter: \t\t\t0.625\""
             "\nBolt Length: \tStud - \t\t3.5\""
             "\n\t\tMachine - \t3\""                          << endl;
        }
        if (pressclass == 2)
        {
            cout << "\n\n*** FLANGE DATA ***"
             "\n____________________"
             "\n\nWeld Neck Raised Face: \t\t3.125\""
             "\nFlange Diameter: \t\t8.25\""
             "\nFlange Thickness: \t\t1.125\""                << endl;

            cout << "\n*** BOLTING DATA ***"
             "\n____________________"
             "\n\nNumber of Bolts: \t\t8"
             "\nBolt Diameter: \t\t\t0.75\""
             "\nBolt Length: \tStud - \t\t4.25\""
             "\n\t\tMachine - \t3.5\""                        << endl;
        }
        if (pressclass == 3)
        {
            cout << "\n\n*** FLANGE DATA ***"
             "\n____________________"
             "\n\nWeld Neck Raised Face: \t\t3.5\""
             "\nFlange Diameter: \t\t8.25\""
             "\nFlange Thickness: \t\t1.25\""                 << endl;

            cout << "\n*** BOLTING DATA ***"
             "\n____________________"
             "\n\nNumber of Bolts: \t\t8"
             "\nBolt Diameter: \t\t\t0.75"
             "\nBolt Length: \tStud - \t\t5\""                << endl;
        }
        if (pressclass == 4)
        {
            cout << "\n\n*** FLANGE DATA ***"
             "\n____________________"
             "\n\nWeld Neck Raised Face: \t\t4.25\""
             "\nFlange Diameter: \t\t9.5\""
             "\nFlange Thickness: \t\t1.5\""                  << endl;

            cout << "\n*** BOLTING DATA ***"
             "\n____________________"
             "\n\nNumber of Bolts: \t\t8"
             "\nBolt Diameter: \t\t\t0.875"
             "\nBolt Length: \tStud - \t\t5.75\""             << endl;
        }
        mm_choice = 5;
    }
    if (mm_choice == 3)
    {
        int valvetype;

        valvetype = get_valve_type();

        if (valvetype == 1)
        {
            if (pressclass == 1)
            {
                cout << "\n\n*** GATE VALVE DATA ***"
                        "\n____________________"
                        "\n\nButt-Weld Overall Length: \t\t11.125\""
                        "\nFlanged Overall Length: \t\t8\""          << endl;
            }
            if (pressclass == 2)
            {
                cout << "\n\n*** GATE VALVE DATA ***"
                 "\n____________________"
                 "\n\nOverall Length: \t\t11.125\""           << endl;
            }
            if (pressclass == 3)
            {
                cout << "\n\n*** GATE VALVE DATA ***"
                 "\n____________________"
                 "\n\nOverall Length: \t\t14\""               << endl;
            }
            if (pressclass == 4)
            {
                cout << "\n\n*** GATE VALVE DATA ***"
                 "\n____________________"
                 "\n\nOverall Length: \t\t14\""               << endl;
            }
        }
        if (valvetype == 2)
        {
            if (pressclass == 1)
            {
                cout << "\n\n*** BALL VALVE DATA ***"
                 "\n____________________"
                 "\n\nRegular Port Overall Length: \t\t8\""
                 "\nFull Port Overall Length: \t\t8\""        << endl;
            }
            if (pressclass == 2)
            {
                cout << "\n\n*** BALL VALVE DATA ***"
                 "\n____________________"
                 "\n\nRegular Port Overall Length: \t\t11.125\""
                 "\nFull Port Overall Length: \t\t11.125\""   << endl;
            }
            if (pressclass == 3)
            {
                cout << "\n\n*** BALL VALVE DATA ***"
                 "\n____________________"
                 "\n\nRegular Port Overall Length: \t\t14\""
                 "\nFull Port Overall Length: \t\t14\""       << endl;
            }
            if (pressclass == 4)
            {
                cout << "\n\n*** BALL VALVE DATA ***"
                 "\n____________________"
                 "\n\nRegular Port Overall Length: \t\t14\""
                 "\nFull Port Overall Length: \t\t14\""       << endl;
            }
        }
        mm_choice = 5;
    }
    if (mm_choice == 4)
    {
        pipe_spacing(ui_nps);
        mm_choice = 5;
    }
    }
    ui_nps = 100;

    return ui_nps;
}


//This function gets the main menu choice from the user
int main_menu(void)
{
    int mm_choice = 0;


    while ((mm_choice > 5) || (mm_choice < 1))
    {
        cout << "\nPlease select an option: "
         "\n1 - Pipe/fitting data"
         "\n2 - Flange/bolting data"
         "\n3 - Valve data"
         "\n4 - Centerline spacing"
         "\n5 - Back"                     << endl;

        cin >> mm_choice;
    }

    return mm_choice;
}

//This function gets the pressure class of the piping system
int get_pressclass(void)
{
    int pressclass = 0;

    while ((pressclass > 4) || (pressclass < 1))
    {
        cout << "\nWhich pressure class is used: "
         "\n1 - 150lb"
         "\n2 - 300lb"
         "\n3 - 600lb"
         "\n4 - 900lb"                            << endl;

        cin >> pressclass;
    }

    return pressclass;
}

//This function gets the valve type for the valve data
int get_valve_type(void)
{
    int valvetype = 0;

    while ((valvetype > 2) || (valvetype < 1))
    {
        cout << "\nPlease select an option: "
         "\n1 - Gate"
         "\n2 - Ball"                     << endl;

        cin >> valvetype;
    }

    return valvetype;
}

//This function will obtain information on pipe spacing based on
//the pipe size it will be beside
float pipe_spacing(float ui_nps)
{
    int choice = 0;
    float ui_nps2, ui_ins1 = 0, ui_ins2 = 0;


    cout << "\nPlease enter NPS of other pipe: "           << endl;
    cin >> ui_nps2;

    while ((choice > 2) || (choice < 1))
    {
        cout << "\nDoes either pipe have insulation?"
         "\n1 - Yes"
         "\n2 - No"                                   << endl;

        cin >> choice;
    }

    if (choice == 1)
    {
        choice = 0;

        while ((choice > 2) || (choice < 1))
        {
            cout << "\nDo both pipes have insulation?"
             "\n1 - Yes"
             "\n2 - No"                               << endl;

            cin >> choice;
        }

        if (choice == 1)
        {
            cout << "\nPlease enter the insulation of both pipes: " << endl;
            cin >> ui_ins1;
            cin >> ui_ins2;

            //If both pipes are under 14" NPS
            if ((ui_nps < 14) && (ui_nps2 < 14))
            {
                pipe_space1(ui_nps, ui_nps2, ui_ins1, ui_ins2);
            }
            //If both pipes are 14" NPS and above
            if ((ui_nps >= 14) || (ui_nps2 >= 14))
            {
                pipe_space2(ui_nps, ui_nps2, ui_ins1, ui_ins2);
            }
        }
        if (choice == 2)
        {
            cout << "\nPlease enter the thickness of insulation on the insulated pipe: " << endl;
            cin >> ui_ins2;

            //If both pipes are under 14" NPS
            if ((ui_nps < 14) && (ui_nps2 < 14))
            {
                pipe_space1(ui_nps, ui_nps2, ui_ins1, ui_ins2);
            }
            //If both pipes are 14" NPS and above
            if ((ui_nps >= 14) || (ui_nps2 >= 14))
            {
                pipe_space2(ui_nps, ui_nps2, ui_ins1, ui_ins2);
            }
        }
    }
    if (choice == 2)
    {
        //If both pipes are under 14" NPS
        if ((ui_nps < 14) && (ui_nps2 < 14))
        {
            pipe_space1(ui_nps, ui_nps2, ui_ins1, ui_ins2);
        }
        //If both pipes are 14" NPS and above
        if ((ui_nps >= 14) || (ui_nps2 >= 14))
        {
            pipe_space2(ui_nps, ui_nps2, ui_ins1, ui_ins2);
        }
    }
    return 0;
}

//Function to space pipes under 14" NPS
float pipe_space1(float ui_nps, float ui_nps2, float ui_ins1, float ui_ins2)
{
    float outside_dia1, outside_dia2, ps_factor1 = 3.5;
    float pipe_space1;

    outside_dia1 = (ui_nps + (ui_ins1*2));
    outside_dia2 = (ui_nps2 + (ui_ins2*2));

    pipe_space1 = ((outside_dia1 / 2) + (outside_dia2 / 2) + ps_factor1);

    cout << "\nCenterline to Centerline spacing is: " << pipe_space1 << "\"" << endl;

    return 0;
}

//Function to space pipes if one pipe is above 14" NPS
float pipe_space2(float ui_nps, float ui_nps2, float ui_ins1, float ui_ins2)
{
    float outside_dia1, outside_dia2, ps_factor1 = 4.5;
    float pipe_space1;

    outside_dia1 = (ui_nps + (ui_ins1*2));
    outside_dia2 = (ui_nps2 + (ui_ins2*2));

    pipe_space1 = ((outside_dia1 / 2) + (outside_dia2 / 2) + ps_factor1);

    cout << "\nCenterline to Centerline spacing is: " << pipe_space1 << "\"" << endl;

    return 0;
}
