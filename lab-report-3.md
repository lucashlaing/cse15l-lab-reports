# Lab Report 3
## Part 1: Bugs


For bugs, we will be looking at the  `reversed` method from week 4. It is supposed to reverse the array that is passed in as a parameter. For example, an array with the elements `{1, 2}` should change to `{2, 1}` after a call to the  `reversed` method with said array as an argument. However, this method does not work as intended.


### A failure-inducing input
```
  @Test 
  public void testReverseInPlace() {
    int[] input1 = { 3,5,1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1,5,3 }, input1);
  }
```


### An input that does not cause a failure 

```
  @Test 
  public void testReverseInPlace2() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
  }
```


### The initial code that was causing the failure
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```


### The fixed version of the code
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[arr.length- i - 1];
      arr[arr.length- i - 1] = arr[i];
      arr[i] = temp;
    }
  }
```


The problem with the initial code was taking the elements from the end of the array and putting them at the front of the array. However, once we get to the second half of the array, we realize that the elements initially at the start of the array have been overwritten and therefore cannot be copied to the back. This just creates an array which is like a palindrome. Our code fixes the problem because we only go to half the array. We start from both ends and swap each of these elements with one another. This ensures we have all the data we need and nothing gets overwritten before it is put into another spot.


## Part 2: Researching Commands


For this part, we will be looking at the command `grep`. These command line options were found [from the geeksforgeeks website here.](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

### `grep -i`

#### Example 1
```
minzi@Lucas-Laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch/technical/government/Alcohol_Problems (main)
$ grep -i Abuse Session3-PDF.txt 
and his or her drinking or drug abuse and may be more motivated to
of a substance abuse counselor mobilizing the family, and at times
arrange for immediate entry to a residential substance abuse
examined the outcomes achieved by substance abuse counselors or
agreed to be in the program.21 A substance abuse consultation team
specialists trained in alcohol or substance abuse counseling or in
directly, and offered some advice and assistance. Substance abuse
avoid alcohol-related injuries in the future. Substance abuse
substance abuse interventions focus on motivation to enter
substance abuse counselors, only 5% used screening questionnaires
abuse/dependence is a "treatable disease," but more than 90%
substance abuse counselors. However, it may be more a matter of
been published that deal with alcohol dependence and abuse and
fatal disease."52 More recently, the Substance Abuse Task Force
abuse/dependence in motor vehicle crash victims presenting to the
alcohol abuse in trauma patients. Arch Surg 1993;128:907-13.
Abuse Task Force. Society for Academic Emergency Medicine. Acad
Substance Abuse Task Force. Society for Academic Emergency
alcohol-related injuries. Substance abuse interventions in general
substance abuse.
22. El-Guebaly N, Armstrong SJ, Hodgkins DC. Substance abuse
abuse consultation team in a trauma center. J Stud Alcohol
preventive services, and the substance abuse treatment system. Ann
39. Center for Substance Abuse Treatment, Substance Abuse and
attitudes concerning intervention for alcohol abuse/dependence in
◆Substance Abuse Evaluation and Referral
of primary care with the emergency room. J Subst Abuse
services, and the substance abuse treatment system. Ann Emerg Med
clinicians in screening and brief intervention for substance abuse
problems: translating evidence into practice. J Subst Abuse
to alcohol misuse and abuse.
alcohol-related injuries. Substance abuse interventions in general
care, but of many systems. Her work has been in substance abuse
```


This is finding all the lines where abuse was written, regardless of upper or lower case. This is useful because we could miss some words if we did not have this command line option. 

#### Example 2

```
minzi@Lucas-Laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch/technical/government/About_LSC (main)
$ grep -i jUsTice diversity_priorities.txt 
On May 31 and June 1, 2001, approximately fifty equal justice
overcome the challenges and obstacles, and to promote justice,
eradication of poverty and promoting equality and justice and
Justice Violence Against Women Office) "old" funders (LSC, United
growth of state justice communities and the many stakeholders
our vision for inclusion as a justice imperative.
Making justice communities more diverse, inclusive and
ensure that both individual state justice communities and the
justice could be defined. Indicators are grouped by topic and
meeting goals that ensure our programs and state justice
State Justice Communities
achieve it. Programs and state justice communities seek guidance on
affirmative duty to address barriers. Program and justice community
State justice communities begin to examine how they set
strategies in addressing community problems. State justice
Ensuring that Justice Communities Become Diverse, Inclusive, and
and racial justice)
justice community is that it is diverse, inclusive, and
are regular diversity conferences for state justice community
```
This finds all the instances of the word "justice" in this file regardless of the case. This command line option can also be useful when we end up capitalizing our arguments in weird places. 


### `grep -n`

#### Example 1
```
minzi@Lucas-Laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch/technical/biomed (main)
$ grep -n development 1471-213X-1-2.txt 
7:        cellular behaviors. It is essential for animal development,
35:        stages of development by fluorescence microscopy of GFP
113:        in development,
```
This find all instances of "development" in the file and tells which line it is located in. This is useful since it allows us to easily locate each instance. 

#### Example 2
```
minzi@Lucas-Laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch/technical/biomed (main)
$ grep -n gene 1471-213X-1-9.txt
11:        the absence of external cues [ 1, 2]. Molecular-genetic
15:        3, 4, 5] that rhythms of gene expression are of central
16:        importance both in the sustained generation of rhythmicity
17:        (clock genes) and in the control of output pathways (clock
18:        controlled genes).
24:        originally characterized as central clock genes in
38:        rhythmic gene transcription appears to be of central
40:        regulation of the transcription of "clock controlled" genes
51:        that rhythmic gene expression occurs more broadly. For
56:        circadian transcription of the clock gene,
60:        identification of period gene homologues in mammals has led
66:        nocturnin gene was discovered in a
67:        differential display screen for circadian gene expression
69:        Xenopus laevis [ 35, 36]. The gene
76:        to affect gene transcription through interactions with
83:        increased gene transcription [ 36].
85:        nocturnin gene appears to encode a
98:        other clock-related genes in the mouse, indicating that
149:          Xenopus [ 36] and mouse [ 39] genes
179:          using single stranded probes generated from the
260:          Laboratory strains of mice are heterogeneous in the
263:          nocturnin/CCR4 gene. During the
268:          mNoc/CCR4 gene. In DBA/2, BALB/c,
368:        clock-regulated genes [ 35, 36] in the retina of the
374:        night was found to be a defining feature of the gene.
378:        gene transcription. Furthermore,
408:        factor required for the transcription of genes including
445:        Xenopus embryogenesis (Green,
463:        Drosophila central "clock gene",
466:        period gene is rhythmically expressed
473:        controlled" gene, perhaps coupling clock activity to an
483:        function in a general way as either a central clock
489:        nocturnin/CCR4 gene. Furthermore, it
500:        nocturnin/CCR4 gene was apparently a
509:        this gene.
535:        mNoc gene during the process of aging
542:        as a rhythmic gene product in photoreceptors, the most
546:        nocturnin as a rhythmic gene product
547:        in rat liver and kidney based gene array analysis of over
548:        9000 rat Unigenes (Kita, et al., unpublished).
550:        among a group of clock-regulated genes that included
558:        clock genes in peripheral tissues [ 7, 8, 10, 11, 12].
560:        that circadian oscillation of gene expression in the liver
638:          [ 39]) identified in the nocturnin/CCR4 gene. The forward
652:          mNoc were generated using a
665:          NucTrap gel filtration columns (Stratagene, La Jolla,
674:          protocol (Stratagene, La Jolla, CA). Nylon membranes were
692:          Degenerative PCR was carried out using Taq DNA
710:          cloned into the pBluescript KS (+) vector (Stratagene)
```
This finds all the instances of "gene" in the text and tells us which line number it is at. This could be useful when dealing with large code files so we know exactly where to find a variable being used. 

### `grep -r`

#### Example 1
```
$ grep -r tumours ./
./journal.pbio.0020040.txt:        tumours in these predisposed patients, the remaining wild-type copy of the tumour
./journal.pbio.0020040.txt:        EMBO Journal describing a detailed study of tumours in mice lacking one
./journal.pbio.0020040.txt:        Trp53 wild-type allele in the tumours. According to the two-hit model, it
./journal.pbio.0020040.txt:        was expected that in these tumours this copy would have been lost or inactivated. However,  
./journal.pbio.0020040.txt:        this turned out not to be the case. Half of the tumours from mice younger than 18 months    
./journal.pbio.0020040.txt:        two tumours, the researchers sequenced the complete coding region of the remaining
./journal.pbio.0020040.txt:        tumours was expressed normally and suggested it had a normal wild-type conformation.        
./journal.pbio.0020040.txt:        first tested whether the tumours showed amplification of Mdm2. This protein, whose
./journal.pbio.0020040.txt:        feedback mechanism that keeps p53 levels low. Some tumours therefore amplify the
./journal.pbio.0020040.txt:        the tumours from the
./journal.pbio.0020040.txt:        p53-dependent apoptosis, and, indeed, in tumours that had retained the wild-type allele,    
./journal.pbio.0020040.txt:        irradiation did lead to an increase in apoptosis, whereas in tumours that had lost the      
./journal.pbio.0020040.txt:        Pcna ) in p53-positive tumours after irradiation and showed responses
./journal.pbio.0020040.txt:        tumours was able to bind to a p53-binding DNA sequence in an in vitro setting. Finally,     
./journal.pbio.0020040.txt:        since it is known that p53 absence in tumours is correlated with chromosomal instability,   
./journal.pbio.0020040.txt:        between p53-negative and p53-positive tumours and found a 5-fold greater stability in the   
./journal.pbio.0020040.txt:        +/− tumours the wild-type allele of
```
This finds all instances of the word tumour in the directory `/plos`. This is useful when we want to find a certain word in several different files

#### Example 2
```
minzi@Lucas-Laptop MINGW64 ~/OneDrive/Documents/GitHub/docsearch/technical/plos (main)
$ grep -r Alfred ./
./journal.pbio.0020040.txt:        postulated in Alfred Knudson's (1971) two-hit model. And, indeed, it was shown that in the
./journal.pbio.0020306.txt:        marine ecologist Christian Hamm (Alfred Wegener Institute for Polar and Marine Research,
./journal.pbio.0030032.txt:        PSMs are two-year American master's degrees financed in large part by the Alfred P.
./pmed.0010013.txt:        consider Dennis Burkitt's report on jaw tumors in African children, Alfred Blalock's
```
This finds all mentions of "Alfred" in the directory `/plos`. This helps find how many times a certain researcher or research paper is mentioned. 
