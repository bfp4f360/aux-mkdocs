
# <span style="color:gold">Welcome to 501st Aux mod Mkdocs site</span> 	
Hello this is a simple mkdocs site for the 501st Aux mod. Here I will post any major changelogs and other information for the unit.	

Also this is the link to the fancy mkdocs site [here](https://aux-mkdocs.readthedocs.io/en/latest/)	
	
## <span style="color:gold">Mod links </span> 	
- This [here](https://steamcommunity.com/sharedfiles/filedetails/?id=1847261252) is the live aux mod. It will generaly update every Sunday, unless there is a big bug to fix.	
- This [here](https://steamcommunity.com/sharedfiles/filedetails/?id=1895624803) is the dev aux mod. It will generally update every day or so to preview whats coming up and fix bugs.	
## <span style="color:gold">Other mod permissions</span> 	
There are some things in this mod that I didnt make my self that where made by others. These are the things I didnt make my self that I asked if I could put in this mod, atleast the big ones I remember there might be stuff I found on forums that I simply cant remember or because I am human.	
??? info "Blast Refraction"	
    ### Blast Refraction	
    This basicly adds a refraction effect to most explosives. It was made by Taros from CUP, and as such its pretty fucking lit.	
    [Here](https://forums.bohemia.net/forums/topic/221306-refraction-blast-wave/) is a link to the BI forum about it.  	
    ![Screenshot](https://media.discordapp.net/attachments/457505629729325056/651622366010540042/blast_effect.PNG)	
??? info "BF3 style thermals"	
    ### BF3 style thermals	
    This mod basicly edits the thermal file to add on a bf3 style thermal. Now normally instead of putting someone elses mod in yours, you would just list it as a dependency or something. However due to the way thermals work in Arma as its a png file, you cant do that. So I asked the creator if I could add his thermal colors in. [Heres](https://steamcommunity.com/sharedfiles/filedetails/?id=1799993760) the original steam page.	
    ![Screenshot](https://cdn.discordapp.com/attachments/457505629729325056/651622366895538176/thermal.PNG)	
??? info "Aircraft Boost script"	
    ### Aircraft Boost script	
    I started modding in Arma because of this lol. while this isnt just yet,I would like to make my own but these guys made a pretty good one better then anything I could make so I ask if I can edit and use it. [Heres](https://steamcommunity.com/workshop/filedetails/?id=743099837) the mod.	
    ![Screenshot](https://cdn.discordapp.com/attachments/457505629729325056/651622368103497738/afterburner.PNG)	
## <span style="color:gold">Jumppack</span> 	
I suspect that alot of ppl outside will like the jumppack, so assuming you are willing to use SWOP (**dies inside**) you can do the following to have our own jumppack. ==NOTE:== I will soon make a standalone mod for non swop ppl soooon when I get time and not memeing.	
??? info "Inheritance for own jumppack"	
    ### Example config.cpp	
    ```cpp	
    class CfgPatches	
    {	
        class my_cool_jumppack_patch	
        {	
            author="UR NAME HERE	
            requiredAddons[]=	
            {	
                "RD501_patch_particle_effects"	
            };	
            requiredVersion=0.1;	
            units[]={	
            };	
            weapons[]={};	
            vehicles[]={	
            "my_cool_jumppack"	
            };	
        };	
    };	
    class CfgVehicles	
    {	
        class RD501_jumppack_neutral_base;	
        class my_cool_jumppack: RD501_jumppack_neutral_base	
        {	
            scope = 2;	
            displayname = "WOWE JUMPZ ARE COOL";	
            RD501_jumppack_is_jumppack = 1;//(no=0,yes=1)	
            RD501_jumppack_spam_delay = 1;//in seconds	
            RD501_jumppack_energy_capacity = 100; //like fuel in a car	
            RD501_jumppack_recharge = 4; //energy regain per second	
            //for now dont change	
            RD501_jumppack_jump_effect_script = "RD501_jumppack_fnc_effect_jt_21";	
            //for now dont change	
            RD501_jumppack_effect_points[] = {{"spine3",{0,-0.3,-0.1}}};	
            RD501_jumppack_sound_ignite[] = {"RD501_Jumppack\sounds\cdv21Start.ogg"};	
            RD501_jumppack_sound_land[] = {"RD501_Jumppack\sounds\cdv21End.ogg"};	
            RD501_jumppack_sound_idle[] = {"RD501_Jumppack\sounds\cdv21Idle.ogg"};	
            //Each index in this array is a jump type.	
            RD501_jumppack_jump_types[] = {	
                {	
                    "Forward Jump", // Name of jump	
                    {	
                        12,		    //forward velo(in m/s)	
                        20,		    /verticle velo(in m/s)	
                        50,			//cost	
                        0,			//angle(degrees)	
                        0,			//directional(no=0,yes=1)	
                        0			//can prone jump(no=0,yes=1)	
                    }	
                },	
                ,{"Short Jump",{12,5,30,0,1,0}}};	
            	
            model = "SWOP_clones\clonebackDV.p3d";//OR whatever model u want	
            maximumload = 700;	
        };	
    };	
    ```
