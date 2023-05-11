# Using The Grep Command
the grep command in its default mode takes in a file and string argument. 
It then proceeds to search and print all lines of the text file that contains the given string
## -i option

### Example 1
**Input: **

```grep -i Plasma rr74.txt```

**Output: **

 ```
 min, and plasma removed and frozen. Later, samples were
          thawed and centrifuged at 15,000 rpm for 20 min. Plasma
          Plasma samples 1 μl were added to 2 ml vanadium III
          increased NO, we measured plasma NO metabolites (Fig. 5).
        arterial plasma nitrite levels [ 41]. Following chronic
        et al. [ 42] found that plasma NO
        previous studies, the plasma NO metabolite content in the
        account for the slight increase in plasma NO metabolites
        and pulmonary vasculatures can both contribute to plasma NO
        investigators did not observe any difference in plasma NO
 ```
The -i option for the grep command works mostly the same as grep without any option. The only difference is, 
the proccess in which it searches and prints out lines in the text file containing the given string argument is NOT case sensitive.
The above example shows how I was given lines in the text file which contains the string argument I provided which is "PLASMA", while ignoring rules of case sensitivity. 
This option for the grep command is useful in this situation if you want to find and line in the text file that contains the string plasma without caring about the case sensitivity.
As you can see in the above output certain lines contains the string "Plasma" with a capital P and "plasma" wihout capitalization, so I would not have received the same input when leaving out the -i option.

### Example 2

**Input: **

```grep -i was rr74.txt```

**Output: **
```
(simulating sea level). Exposure was continuous, with
          was removed and animals were sorted by sex. At 6 weeks
          RVsP was measured as previously described [ 9].
          breathing room air, and a 26-gauge needle was introduced
          approach; RVsP was recorded. Blood was drawn and animals
          were killed. The thorax was opened and the lungs were
          flushed with cold PBS. The right lung was frozen for
          protein and RNA measurement, and the left lung was fixed
          Frozen lung tissue was homogenized in ice cold 750 μl
          methylsulfonyl fluoride was added. Samples were
          concentration was determined using the Bradford method
          USA). Coomassie blue staining was used to verify equal
          washed and incubated with secondary antibody (1:1500
          (Amersham Pharmacia Biotech). INOS-positive control was
          nNOS-positive control was mouse brain protein.
          Total RNA was extracted from 100 mg of frozen lung
          Cincinnati, OH, USA) and the final product was
          2 O. RNA was quantified and samples
          Biosystems, Foster City, CA, USA). RNA quantity was
          Message abundance was determined by dividing the quantity
          Heparinized blood 100 μl was placed in capillary tubes
          The remainder of the blood was spun at 4000 rpm for 10
          reduce all NO metabolites to NO. NO was driven into the
          RVsP was measured as an index of pulmonary arterial
          pressure. As shown in Fig. 1, RVsP was elevated in
          However, iNOS protein was below the limit of detection
          was lipopolysaccharide-treated mouse spleen) and using
          shown), and nNOS was unchanged among the three
          experimental groups (positive control was mouse
          quantitative reverse-transcription PCR, was increased
          conditions, whereas iNOS expression was increased
          Localization of NOS in mouse lung was determined using
          staining was more intense in large vessels and extended
          out to the periphery of the lung, and was also found in
          not increase following exposure to hypoxia. This was
          There was a modest increase in levels of NO metabolites
        The major finding of this work was the upregulation of
        increased eNOS was correlated with increased
        however, was not observed for iNOS or nNOS. Additionally,
        from birth was more severe than we had observed in previous
        degree of polycythemia was also greater in these animals
        physiologic stress that was not seen in more mature animals
        was not sufficiently severe to decrease survival during the
        of eNOS protein was increased in hypoxic, hypertensive rat
        lungs, and that this was not entirely due to the presence
        of hypertension and increased shear stress, but was also
        production was not increased (see below) or that NO was
        was increased but iNOS protein remained below the limit of
        iNOS mRNA levels was not associated with detectable iNOS
        iNOS protein levels in adult mice following hypoxia was
        waste products, including ammonia, that may contribute to
        that lung iNOS protein was detectable only after
        In rat lungs, nNOS expression was increased following
        endothelium-dependent vasorelaxation, whereas there was an
        present study was minimally elevated in the hypoxic group.
        metabolite levels, if NOS was downregulated in the systemic
        NOS was downregulated, but did observe a decrease in
```

In the second example above I once again use the option -i along with my string argument "was" along with the desired text file to be searched.
This is despite the fact that the lines printed out does not contain the string "was" with the same case sensitivity as the inputted string for reasons previously explained.
However unlike the previous example the -i command is technically not needed as i could use the command using a string input of "was" and would likely get the same output. 
However it is still useful to use incase that is not true, as the person using the grep command may not know what the contents of the file were prior to using the command.


## -v option

### Example 1

**Input: **

```grep -v e rr73.txt```

**Output: **
```
Introduction







          10, 11].






          not shown).
          shown).


          In contrast, PGE


          PGE



        Discussion


        Conclusion
        PGE


        2 = prostaglandin E
        2 .






            2 (PGE




            Tris-HCl, pH 7.5, containing 6 mM CaCl
            2 and 1 μM ZnCl) for 18 hours at
            CA, USA).
```

In the above example the -v option for the grep command uses the string argument to search and print all lines inside the given text file that does NOT contain the given string.
This has the reverse effect of the grep commands default behavior, printing out all lines that it would otherwise exclusively NOT print. This option is very useful in this situation
since I want to find all lines in the text file that does NOT include the string "e" rather than lines that do.

### Example 2

**Input: **

```grep -iv e rr73.txt```

**Output: **

```
Introduction







          10, 11].






          not shown).
          shown).







        Discussion


        Conclusion


        2 .










            Tris-HCl, pH 7.5, containing 6 mM CaCl
            2 and 1 μM ZnCl) for 18 hours at
            CA, USA).
```

The above second example is similar to the first except the command contains the option "-iv" which is just the combination of the option -i and -v.
Given that it is a combination of those 2 options it will only search and print lines from the text file that does not contain the string "e" regardless of its Capitilization.
This is useful for if you want to not only exclude any line with the string "e", but all lines where the letter e occurs at all despite it being capitalized or not.

## -w option

### Example 1

**Input: **

```grep -w NO rr74.txt```

**Output: **

```
NO, which may be synthesized by any of the three
        circulation in many mammals. NO has been proposed as a
        2] suggested that inhibition of NO increases acute hypoxic
        NO is important in modulating basal pulmonary vascular
          NO metabolites (NO, NO
          2 -, NO
          were measured using a NO chemiluminescence analyzer
          reduce all NO metabolites to NO. NO was driven into the
          increased NO, we measured plasma NO metabolites (Fig. 5).
          There was a modest increase in levels of NO metabolites
        severe pulmonary hypertension; this suggests either that NO
        production was not increased (see below) or that NO was
        production of NO
        decreased exhaled NO and decreased aortic and pulmonary
        et al. [ 42] found that plasma NO
        NO production despite the increase in NOS expression. There
        NO production and increased NOS expression
        previous studies, the plasma NO metabolite content in the
        account for the slight increase in plasma NO metabolites
        and pulmonary vasculatures can both contribute to plasma NO
        increased NO metabolites could also be due to decreased NOS
        investigators did not observe any difference in plasma NO
        acetylcholine-stimulated NO release from aortic rings. The
        oxide synthase; NO = nitric oxide; NOS = nitric oxide
```

In the above example the -w option for the grep command searches for and prints all lines in the text file that contain not just the string itself, but the given string as a word.
The -w option is useful in this example since there are words such as "NOS" in this file that contain the string "NO". Having those lines printed out would be invalid since i only want to print lines that contain the WORD "NO".

### Example 2

**Input: **

```grep -wi no rr74.txt```

**Output: **

```
NO, which may be synthesized by any of the three
        circulation in many mammals. NO has been proposed as a
        2] suggested that inhibition of NO increases acute hypoxic
        NO is important in modulating basal pulmonary vascular
          NO metabolites (NO, NO
          2 -, NO
          were measured using a NO chemiluminescence analyzer
          reduce all NO metabolites to NO. NO was driven into the
          increased NO, we measured plasma NO metabolites (Fig. 5).
          There was a modest increase in levels of NO metabolites
        [ 9]. No animals died, however, suggesting that the stress
        severe pulmonary hypertension; this suggests either that NO
        production was not increased (see below) or that NO was
        production of NO
        decreased exhaled NO and decreased aortic and pulmonary
        et al. [ 42] found that plasma NO
        NO production despite the increase in NOS expression. There
        NO production and increased NOS expression
        previous studies, the plasma NO metabolite content in the
        account for the slight increase in plasma NO metabolites
        and pulmonary vasculatures can both contribute to plasma NO
        increased NO metabolites could also be due to decreased NOS
        investigators did not observe any difference in plasma NO
        acetylcholine-stimulated NO release from aortic rings. The
        oxide synthase; NO = nitric oxide; NOS = nitric oxide
```

In the above example I use the -wi option (a combination of the -w and -i option) for the grep command which searches for and prints all lines in the text file that contains the word "no" regardless as to if
any part of the word "no" is capitalized. The output above is the same as in the first example except for one line. However even without that one different line, using the -w command with -i can still be useful
since not always will you know all the contents inside a text file, thus if for whatever reason there is a line that is not fully capitlized like in this second example, you wont see all the lines you were looking for.

## -c option

### Example 1
**Input: **

```grep -c and rr37.txt```

**Output: **

```
102
```
In the above example I use the -c option with the grep command. This option is quite different from the previous ones so far as it does not actually print any lines from the given txt file.
It searches the file you give it for the string you give it, but rather than printing out all of the lines that contains the string, it prints the quantity of lines that contain the string.
This is very helpful for when you need to know the quantity of lines that contain a given string rather than simple veiwing all that lines tha do. A reason for this is because counting all the lines manually can be very
time consuming and especially pointless when this option exists.

### Example 1
**Input: **

```grep -cw and rr37.txt```

**Output: **

```
97
```

In the second example I use the -cw option which is a combintation of the -c command and -w command. This command is much like the command from the first example except it finds the quantity of lines that contain a given
WORD rather than simply the string itself. This is helpful if all you need to know is the quantity of lines that contain a word, but you also dont want to include in the results lines that contain the string you provided rather than the word.

