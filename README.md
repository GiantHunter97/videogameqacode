#include<iostream>
using namespace std;

void line();

void raceDescriptions(int,string);
void questions(string);
void bloodlines(int);
void bloodlineDescription(int, int, string);
void classDescriptions(int, string);

int main() 
{ 
    //string charInfo
    string name, charInfo[4], qa, gender;
    int race, bloodline, Class;
    char char_gender;
    //Part #1 Introductions
               //-------------------------------------------------------------------------------------------------------------------- -
        line();
        cout <<"\tHello there...It seems that you have been summoned to this world or got reincarnated. By one way or another you seem\n"
              "\tto not exactly BE from this world.Despite this my conscious is linked to yours yet I can work independently.\n"
              "\tEven so I can\'t figure out how you look or what make you, YOU.Let\'s start with the basics."<<endl;
               //-------------------------------------------------------------------------------------------------------------------- -
        line();
        cout << "\tWhat is your name?\n\t   ";
        cin >> name;
               //-------------------------------------------------------------------------------------------------------------------- -
        line();
        cout <<"\tSo your name is " << name << ". That is an interesting name, might be odd in this world but we still haven\'t\n"
               "\tseen much of it. Might as well start the next part, it\'s very critical to your appearance and physique." << endl;
               //-------------------------------------------------------------------------------------------------------------------- -
        line();
        do
        {
            cout << "\tWhat is your gender?\n\t";
            cin >> char_gender;
            if (char_gender=='M'|| char_gender == 'm')
            {
                gender = "Male";
            }
            else if(char_gender == 'F'|| char_gender == 'f')
            {
                gender = "Female";
            }
            else
            {
                cout << "Please give me an answer" << endl;
            }
        } while (!(char_gender=='M'|| char_gender == 'm'|| char_gender == 'F'|| char_gender == 'f'));
               //-------------------------------------------------------------------------------------------------------------------- -
        line();
        cout << "\tOkay, so your "<<gender<<", and your name is "<<name<<". We\'re making great progress so let\'s start with how\n"
                "\tyou do you look according to this world\'s standards. I\'m gonna give you a brief description of the races\n"
                "\tI know. My knowledge is very short because of  the situation we find ourselves in." << endl;
               //-------------------------------------------------------------------------------------------------------------------- -
        line();
        system("pause");
        line();
        //Part #2 Race
        line();
        cout << "\tFirst, tell me your race, this determines your appearance and a starting point of how you look." << endl;
        line();
        do{
            do
            {
                cout << "\t1 - Humans\n"
                        "\t2 - Elves\n"
                        "\t3 - Dwarfs\n"
                        "\t4 - Beast" << endl;
                cout << "\tSo, what is your race? ";
                cin >> race;
            } while (!(race<=4||race>=1));
            line();
            raceDescriptions(race,charInfo[1]);
            line();
            cout << "Is this your race?";
            cin >> qa;
            questions(qa);
            line();
        } while (!(qa== "Yes" || qa== "yes" || qa== "YES" || qa== "YEs" || qa== "yEs" || qa== "yeS" || qa== "YeS" || qa== "yES"));
        
             //-------------------------------------------------------------------------------------------------------------------- -
        cout << "\tYou’re a " << charInfo[1] << " quite the physique. As we walk through the land we’ll get several descriptions\n"
                "\tof their relationships with others. We’ll be able to see how we fit in but your actions are your own so\n"
                "\tbe careful what you do as a " << charInfo[1] << ". Either way we still need to determine your bloodline. " << endl;
        line();
        system("pause");
        line();
        //Part#3 Bloodline
             //-------------------------------------------------------------------------------------------------------------------- -
        do
        {
            do
            {
                cout << "\tBloodlines determine your abilities in this world, how your body is going to defend itself in this world.";
                bloodlines(race);
                cout<< "\tSo, what’s your bloodline?";
                cin >> bloodline;
            } while (!(bloodline <= 3 || bloodline >= 1));
            line();
            bloodlineDescription(race, bloodline, charInfo[2]);
            line();
            cout << "Is this your bloodline?";
            cin >> qa;
            questions(qa);
            line();
        } while (!(qa == "Yes" || qa == "yes" || qa == "YES" || qa == "YEs" || qa == "yEs" || qa == "yeS" || qa == "YeS" || qa == "yES"));
                 //-------------------------------------------------------------------------------------------------------------------- -
        cout << "\tInteresting, so you’re a " << charInfo[2] << ".I got a clear view of what you are, you’re a " << gender << "\n"
                "\trace who’s bloodline is " << charInfo[2] << ".So al that’s left is you class, in this world you’ll fight monsters\n"
                "\tand survive dreaded situations. Clearly you must have some sort of skills, I’ll give you some options, choose the\n"
                "\tones that fit your abilities. " << endl;
        line();
        system("pause");
        line();
        //Part#4 Class
        do
        {
            do
            {
                cout << "\t1-Warrior\n"
                        "\t2-Rogue\n"
                        "\t3-Caster\n";
                cout << "\tWhat best describes you? ";
                cin >> Class;
            } while (!(Class<= 3 || Class>= 1));
            line();
            classDescriptions(Class, charInfo[4]);
            line();
            cout << "Is this your class? ";
            cin >> qa;
            questions(qa);
            line();
        } while (!(qa == "Yes" || qa == "yes" || qa == "YES" || qa == "YEs" || qa == "yEs" || qa == "yeS" || qa == "YeS" || qa == "yES"));
        
        system("pause");

        return 0;
}

void line() {
    cout << "\t----------------------------------------------------------------------------------------------------------------------"<<endl;
}

void raceDescriptions(int race, string charRace) {
               
    if (race==1)
    {    
        charRace == "Human";
        cout << "\tHumans are very common in this world, they are resourcefuland have built many settlementsand civilizations around\n"
                "\tthis world, both smalland big. ";
    }
    else if(race==2)
    {
        charRace == "Elf";
        cout << "\tElves are the oldest of all races and are wise and depicted by their ears. They’re very akin to the world’s\n"
                "\tnature and wise as well.";
    }
    else if (race==3)
    {
        charRace == "Dwarf";
        cout << "\tDwarfs are noticeably short and expert forgers, crafters and artists. They don’t get along with others unless they\n"
                "\tearn they’re trust, above that they’re also materialistic and hardworkers. ";
    }
    else if (race==4)
    {
        charRace == "Beast";
        cout << "\tBeasts are different in shape and size, some have feathers others scales. Even, so they have one thing in common,\n"
                "\tthey have animalistic characteristics or descendants from a mythic beast.";
    }
    else
    {
        cout << "\tPlease make sure you choose a race.";
    }
    cout << endl;
}

void questions(string qa) {
    if (!(qa == "Yes" || qa == "yes" || qa == "YES" || qa == "YEs" || qa == "yEs" || qa == "yeS" || qa == "YeS" || qa == "yES" || qa == "no" || qa == "NO" || qa == "No" || qa == "nO"))
    {
        cout << "\tPlease use a proper answer." << endl;
    }
    else if (qa == "no" || qa == "NO" || qa == "No" || qa == "nO")
    {
        cout << "\tThen choose again." << endl;
    }
}

void bloodlines(int race) {

    if (race == 1)
    {
        cout << "\tHumans are resourceful and willful most of their skills are survival, gathering and defensive."<<endl;
        cout << "\t1 - Varkaz\n"
                "\t2 - Shazzall\n"
                "\t3 - Zaldin" << endl;
    }
    else if (race == 2)
    {
        cout << "\tElves are very skilled in magic and medicine, most of their skills are magic based and potions."<<endl;
        cout << "\t1 - High Elf\n"
                "\t2 - Wood Elf\n"
                "\t3 - Dark Elf" << endl;
    }
    else if (race == 3) 
    {
        cout << "\tDwarfs are master of the craft, they can make weapons and armor with high proficiency."<<endl;
        cout << "\t1 - Ice Dwarf\n"
                "\t2 - Magma Dwarf\n"
                "\t3 - Geo Dwarf" << endl;
    }
    else if (race == 4)
    {
        cout << "\tBeasts have animal instincts, they can detect danger and are very adept in certain environments."<<endl;
        cout << "\t1 - Dragon Kin\n"
                "\t2 - Falken\n"
                "\t3 - Katrien" << endl;
    }

}

void bloodlineDescription(int race, int bloodline, string charBloodline){
    if (race == 1)
    {
          //--------------------------------------------------------------------------------------------------------------------
        
        if (bloodline == 1)
        {
            charBloodline = "Varkaz";
            cout << "\tVarkaz are often seen in settlement groups and are very buff.\n\n"
                    "\tBranch: Moving tower – They have more defensive skills than your average humans.";
        }
        else if (bloodline == 2)
        {
            charBloodline = "Shazzall";
            cout << "\tShazzall are always on the move and prefer to camp outside the walls of large civilization.\n\n"
                    "\tBranch: Wanderer – They have agile abilities as well as some resistance.";
        }
        else if (bloodline == 3)
        {
            charBloodline = "Zaldin";
            cout << "\tZaldins are descendants of Kline the creator. They’re mostly scholars, warlocks and wizards \n"
                    "\twho develop new magic in many ways.\n\n"
                    "\tBranch: Magus innovation - Each magic branch has more depth and new spells are added.";
        }
    }
    else if (race == 2)
    {

        if (bloodline == 1)
        {
            charBloodline = "High Elf";
            cout << "\tHigh Elves are the eldest of the elves. They are very close with the mana of this world and have\n"
                    "\tancient knowledge.\n\n"
                    "\tBranch: Archaic Magic – Forgotten magic is shown.";
        }
        else if (bloodline == 2)
        {
            charBloodline = "Wood Elf";
            cout << "\tWood Elves are close with nature and have accustomed themselves to it. They have developed various\n"
                    "\therbs and medicines for aid, as well as poisons for protection.\n\n"
                    "\tBranch: Natural Brewer - Enhanced potion making abilities as well as a broader potion index.";
        }
        else if (bloodline == 3)
        {
            charBloodline = "Dark Elf";
            cout << "\tDark Elves are strong and are very determined, especially in combat. They thrive as warriors and are\n"
                    "\teasily triggered.\n\n"
                    "\tBranch: Warrior Spirit – They have more offensive skills as well as buffs.";
        }
    }
    else if (race == 3)
    {
        if (bloodline == 1)
        {
            charBloodline = "Ice Dwarf";
            cout << "\tIce Dwarves live in cold areas and know how to forge ice and water. They prefer an adventurous\n"
                "\tlifestyle where they can enhance their knowledge of the \"cold forge\".\n\n"
                "\tBranch: Artisan of the depths – It’s able to forge weapons and armor from ice and water.";
        }
        else if (bloodline == 2)
        {
            charBloodline = "Magma Dwarf";
            cout << "\tMagma Dwarves live in volcanoes or extremely hot areas, they forge weapons of extremely rare metals.\n\n"
                    "\tBranch: Blaze Master – Able to forge weapons and armor from exquisite metals.";
        }
        else if (bloodline == 3)
        {
            charBloodline = "Geo Dwarf";
            cout << "\tGeo Dwarves live up high in the mountains or beneath the earth where many minerals are found,\n"
                    "\tthey can forge most metals but can even further and make them more than just exquisite.\n\n"
                    "\tBranch: Forgers Pride – Can make exquisite gear.";
        }
    }
    else if (race == 4)
    {
        if (bloodline == 1)
        {
            charBloodline = "Dragon Kin";
            cout << "\tDragon Kin are decedents of dragons and have great pride in it, they’re passive but they\n"
                    "\tstill are able to defend themselves with their claws and scaly wings.\n\n"
                    "\tBranch: Dragon Pride - They have dragon like abilities such as claw attacks and dragon breath.";
        }
        else if (bloodline == 2)
        {
            charBloodline = "Falken";
            cout << "\tFalken are people who’ve developed wings from years of coexistence nature in extremely\n"
                "\thigh places. It all started with a natural mutation but it was simple a blessing from nature.\n\n"
                "\tBranch: Sky Rider – Able to soar and fly indefinitely as well as enhanced view.";
        }
        else if (bloodline == 3)
        {
            charBloodline = "Katrien";
            cout << "\tKatriens are a forgotten race but recently they have emerged from forests and underground\n"
                "\ttunnels. They have feline ears, along with a tail and cat eyes.\n\n"
                "\tBranch: Nocturnal – They see clearly in the dark and crawl silently, they have other catlike traits.";
        }
    }
    cout << endl;
}

void classDescriptions(int Class, string charClass) {
            //-------------------------------------------------------------------------------------------------------------------- -

    if (Class == 1)
    {
        charClass = "Warrior";
        cout<<"\tThe warrior often reside in the frontlines of combat. In it\'s spare time it practices it\'s battle skills and is\n"
            "\table to master heavy sized weapons as well as use weapons along with a shield. This doesn\'t close it\'s magic\n"
            "\tpotential but it excels in weaponry mastery.\n\n"

            "\t Skills:\n\n"

            "\tBattle Cry – In harsh conditions it creates a protective barrier for itself and near allies.\n"  
            "\tImperial Strength – It buffs it’s strength by the number of enemies it’s facing.\n"
            "\tConfidence Boost – People trust you more easily.";
    }
    else if (Class == 2) 
    {
        charClass = "Rogue";
        cout<<"\tThe rogue lives on the edge and it\'s always pushing its limits. Its skill set is very general, it\'s good with\n"
            "\tspells and good with light weapons rather than big ones. This is due to it\'s enhance agility. It\'s able to\n"
            "\tmove at quick speeds and a fast-overall recovery to boot.\n\n"

            "\t Skills:\n\n"

            "\tSurvivalist – Skill CD have a chance to reset and recovery is enhanced.\n"
            "\tTeleport – It uses magic to teleport in certain distances.\n"
            "\tGatherer – Grants extra findings when gathering herbs for potions.";
    }
    else if (Class == 3) 
    {
        charClass = "Caster";
        cout << "\tThe caster uses magic to conjure spells and summoning. It uses magic as offense and defense, but it this\n"
            "\tdoesn’t exclude the ability to wield light weapons such as daggers. Overall, the caster excels at magic\n"
            "\twith a large amount of mana and a good mana regeneration.\n\n"

            "\t Skills:\n\n"

            "\tAncient Wisdom – It debuffs enemies with poison, weaken, low defense, etc.\n"
            "\tPlanner’s intuition – During puzzles or when making decisions you get a hidden hint.\n"
            "\tRapid casting – Spells CD and mana regenerate faster.";
    }
    cout << endl;
}
