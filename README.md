# Response-Generator

//This program will generate a letter of recommendation for the student. The name of the student will be entered by the user and will replace strings that act as placeholders. The user will also select whether the letter will be a positive or negative letter of recommendation. Based on that, random adjectives (positive or negative) will replace some adjectives in the original letter so that there is some uniqueness to each letter. //


#include <iostream>
#include <string>
#include <stdlib.h>
#include <time.h>
using namespace std;

int main()
{
    
    int y;
    
    int x;
    
    
    
    
    string first;
    cout << "What is the student's first name? ";     // Ask the user to input the first name
    getline (cin, first);                             // Take the users input and store it in the "first" variable
    
    string last;
    cout << "What the student's last name? ";          // Ask the user to input the last name
    getline (cin, last);                               // Take the input and store it in the "last" variable
    
    cout << "If this is a good student enter 1. If this is a bad student enter 2: \n";
    
    cin >> y;                 // x determines whether it's a good letter or bad letter
    
    
    string s("\nTo Whom It May Concern:\n I am writing this letter to recommend xx yy as a candidate for graduate school. I am a Professor in the Electrical and Computer Engineering Department at Oceania University, the Computer Science Department at Oceania University, and a Fellow of the Engineering and Science Association.\n I currently serve as the Capstone advisor for xx 's Capstone project and am directing xx in his career development. xx took my Computer Architecture class that I taught in 2015. He/she excelled in this class, performing very well and obtaining high scores for his/her work. Beyond coursework, xx has been engaged in independent research. xx is a very creative individual, who has taken an interest in biomedical circuit designs as the basis for DNA computing. His/her work has involved several inter-related research thrusts aimed at designing more reliable DNA-based computer that can add 8 bit integers. As an example, one of his/her recent works involved developing a DNA-based computer powered by cold fusion. At the heart of such a scheme is the design of a small nuclearreactor that operates at room temperature. I believe this is a particularly novel approach to establish a new computing framework, and one that will generate a significant amount of discussion in the technical community. While a student at Oceania University, xx was employed in various positions including teaching science and engineering to high school students visiting the university during a summer honor's program, and in my laboratory where he/she vigorously swept the floor with an apparatus designed to reduce spatial entropy. He/she accomplished all these tasks with great initiative and with a very positive attitude. Overall, I strongly recommend that you consider xx for admission into your graduate program. His/her ability to formulate problems and devise solutions, combined with his/her adept social skills, makes me convinced that he/she will succeed at your institution.  If you have any further questions about xx, please don't hesitate to contact me at k.mercurial@oceania.edu.\n\nSincerely, \nKevin Mercurial \nProfessor Electrical and Computer Engineering Oceania");
    
    
    //Good letter template
    
    
    string t ("\nTo Whom It May Concern:\n I am writing this letter to recommend xx yy as a candidate for graduate school. I am a Professor in the Electrical and Computer Engineering Department at Oceania University, the Computer Science Department at Oceania University, and a Fellow of the Engineering and Science Association.\n I currently serve as the Capstone advisor for xx 's Capstone project and am directing xx in his/her career development. xx took my Computer Architecture class that I taught in 2015. He/she excelled in this class, performing very well and obtaining high scores for his/her work. Beyond coursework, xx has been engaged in independent research. xx is a very creative individual, who has taken an interest in biomedical circuit designs as the basis for DNA computing. His/her work has involved several inter-related research thrusts aimed at designing more reliable DNA-based computer that can add 8 bit integers. As an example, one of his recent works involved developing a DNA-based computer powered by cold fusion. At the heart of such a scheme is the design of a small nuclearreactor that operates at room temperature. I believe this is a particularly horrible approach to establish a new computing framework, and one that will generate a significant amount of discussion in the technical community. While a student at Oceania University, xx was employed in various positions including teaching science and engineering to high school students visiting the university during a summer honor's program, and in my laboratory where he/she vigorously swept the floor with an apparatus designed to reduce spatial entropy. He/she accomplished all these tasks with great initiative and with a very positive attitude. Overall, I strongly recommend that you do not consider xx for admission into your graduate program. His/she inability to formulate problems and devise solutions, combined with his/her adept social skills, make me convinced that he/she will not succeed at your institution.  If you have any further questions about xx, please do not hesitate to contact me at k.mercurial@oceania.edu.\n\nSincerely, \nKevin Mercurial \nProfessor Electrical and Computer Engineering Oceania");
    
    

    // Bad letter template
    
    
    while (s.find("xx") != string::npos)                     //replaces first name
        s.replace(s.find("xx"), 2, first );
    
    while (s.find("yy") != string::npos)                        // replaces last name
        s.replace(s.find("yy"), 2, last );
    
    while (t.find("xx") != string::npos)                     //replaces first name
        t.replace(t.find("xx"), 2, first );
    
    while (t.find("yy") != string::npos)                        // replaces last name
        t.replace(t.find("yy"), 2, last );
    
    

    
    
    
    if (y==1)
    {
        
        
        {
            srand( static_cast<unsigned int>(time(NULL)));
            x= rand() %5;                                         // Generate a random number. Had some issues and chose 5
            
            if (x==0)
                while (s.find("excelled") != string::npos)
                    s.replace(s.find("excelled"), 8, "mastered" );            //  Change the adjectives randomly
            
            else if (x==1)
                while (s.find("excelled") != string::npos)
                    s.replace(s.find("excelled"), 8, "was exceptional in" );
            
            else if (x==2)
                while (s.find("excelled") != string::npos)
                    s.replace(s.find("excelled"), 8, "was phenomenal in" );
            
            else if (x==3)
                while (s.find("excelled") != string::npos)
                    s.replace(s.find("excelled"), 8, "was extraordinary in" );
            
            
        }
        
        
        
        
        
        if (y==1)
            
            
        {
            
            srand( static_cast<unsigned int>(time(NULL)));
            x= rand() %5;
            
            if (x==0)
                while (s.find("He accomplished all these tasks with great initiative and with a very positive attitude") != string::npos)
                    s.replace(s.find("He accomplished all these tasks with great initiative and with a very positive attitude"), 180, "He accomplished all these tasks with great ease and a great attitude. " );
            
            else if (x==1)
                while (s.find("He accomplished all these tasks with great initiative and with a very positive attituded") != string::npos)
                    s.replace(s.find("He accomplished all these tasks with great initiative and with a very positive attituded"), 180, "He accomplished all these tasks on time and with good effort. " );
            
            else if (x==2)
                while (s.find("He accomplished all these tasks with great initiative and with a very positive attitude") != string::npos)
                    s.replace(s.find("He accomplished all these tasks with great initiative and with a very positive attitude"), 180, "He accomplished all these tasks effortlessly and did a great job. " );
            
            else if (x==3)
                while (s.find("He accomplished all these tasks with great initiative and with a very positive attituded") != string::npos)
                    s.replace(s.find("He accomplished all these tasks with great initiative and with a very positive attituded"), 180, "He accomplished all these tasks with a superb attitude and great determination. " );
            
            
            
            // s.find is used to find the selected string and s.replace will replace the selectred string with the new string
            // 180 is the length or space of the string.
        }
        
        
        
        
        
        if (y==1)
            
            
        {
            
            
            srand( static_cast<unsigned int>(time(NULL)));
            x= rand() %5;
            
            if (x==0)
                
                
                while (s.find("creative") != string::npos)
                    s.replace(s.find("creative"), 8, "unique" );
            
            else if (x==1)
                while (s.find("creative") != string::npos)
                    s.replace(s.find("creative"), 8, "gifted" );
            
            else if (x==2)
                while (s.find("creative") != string::npos)
                    s.replace(s.find("creative"), 8, "special" );
            
            else if (x==3)
                while (s.find("aa") != string::npos)
                    s.replace(s.find("aa"), 8, "hardworking" );
            
            
            
        }
        
        
        if (y==1)
            
        {
        
        cout << s << endl;           // output the final letter
        
        
        }
        
        
        
    }
    
    
    
    // for negative recommendation letters
    
    
    else if (y==2)
    
    
    {
        
        
        
        
        if (y==2)
            
        {
            
            
            srand( static_cast<unsigned int>(time(NULL)));
            x= rand() %5;
            
            if (x==0)
                while (t.find("excelled") != string::npos)
                    t.replace(t.find("excelled"), 8, "failed" );
            
            else if (x==1)
                while (t.find("excelled") != string::npos)
                    t.replace(t.find("excelled"), 8, "was poor in" );
            
            else if (x==2)
                while (t.find("excelled") != string::npos)
                    t.replace(t.find("excelled"), 8, "was horrible in" );
            
            else if (x==3)
                while (t.find("excelled") != string::npos)
                    t.replace(t.find("excelled"), 8, "was terrible in" );
            
            
        }
        
        
        
        
        
        
        if (y==2)
            
            
        {
            
            
            srand( static_cast<unsigned int>(time(NULL)));
            x= rand() %5;
            
            if (x==0)
                
                while (t.find("creative") != string::npos)
                    t.replace(t.find("creative"), 9, "lazy" );
            
            else if (x==1)
                while (t.find("creative") != string::npos)
                    t.replace(t.find("creative"), 9, "annoying" );
            
            else if (x==2)
                while (t.find("creative") != string::npos)
                    t.replace(t.find("creative"), 9, "lost" );
            
            else if (x==3)
                while (t.find("aa") != string::npos)
                    t.replace(t.find("aa"), 9, "destructive" );
            

            
        }
        
        
        
        
        
        if (y==2)
            
            
        {
            
            srand( static_cast<unsigned int>(time(NULL)));
            
            x= rand() %5;
            
            if (x==0)
                while (s.find("He accomplished all these tasks with great initiative and with a very positive attitude") != string::npos)
                    s.replace(s.find("He accomplished all these tasks with great initiative and with a very positive attitude"), 88, "He accomplished all these tasks very poorly. " );
            
            else if (x==1)
                while (s.find("He accomplished all these tasks with great initiative and with a very positive attitude") != string::npos)
                    s.replace(s.find("He accomplished all these tasks with great initiative and with a very positive attitude"), 88, "He did not accomplish all these tasks and failed to live up to expectations. " );
            
            else if (x==2)
                while (s.find("He accomplished all these tasks with great initiative and with a very positive attitude") != string::npos)
                    s.replace(s.find("He accomplished all these tasks with great initiative and with a very positive attitude"), 88, "He did not accomplish these tasks on time. " );
            
            else if (x==3)
                while (s.find("He accomplished all these tasks with great initiative and with a very positive attituded") != string::npos)
                    s.replace(s.find("He accomplished all these tasks with great initiative and with a very positive attituded"), 88, "He did not accomplish these tasks on time. " );
            
            
            cout << t << endl;         // output the final letter
            
        }
        
        
    }
    
    
    
    
    
    
    
    return 0;
    
}







