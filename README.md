# Internet Buzz and the Movie Box Office
# Table of Contents
- [Problem Statement](#prob_stmt)
- [Table of Contents](#table-of-contents)
- [Development](#development)
- [Credit](#credit)

# PROBLEM STATEMENT

In his undergraduate honors thesis, Versaci (2009) investigated what he termed “internet buzz variables” to see whether they
provide any additional predictive information towards a movie's box office revenues (beyond movie characteristics like
genre, actors, budget, etc.). boxOffice.csv contains this data involving 62 movies (all wide-released movies between
November 7, 2008 and April 3, 2009); the variables available (along with their descriptions) are in the table below. We will
conduct the analysis ignoring the “buzz” variables (addict, cmngsoon, fandango, and cntwait3) first.
<TABLE>
  <TR>
    <TH>Variables</TH>
    <TH>Description</TH>
  </TR>
  <TR>
    <TD>box</TD><td>domestic opening weekend box office revenues ($)</td>
  </TR>
  <TR>
    <TD>G<BR>PG<br>PG13<BR></TD><td>binary variables indicating MPAA rating code (if all 3 are 0, the movie is rated R)</td>
  </TR>
  <TR>
    <TD>budget</TD><td>budget production budget (in millions of $)</td>
  </TR>
  <TR>
    <TD>starpowr</TD><td>star power rating based on the Forbes 2009 Star Currency list (range: 0 to 10)</td>
  </TR>
  <TR>
    <TD>sequel</TD><td>binary (1 → sequel; 0 → not a sequel)</td>
  </TR>
  <TR>
    <TD>action<br>animated<br>horror<br>comedy</TD><td>binary variables indicating movie genre (if all 4 are 0, the movie genre was drama) </td>
  </TR>
  <TR>
    <TD>addict</TD><td> number of trailer views at traileraddict.com</td>
  </TR>
  <TR>
    <TD>cmngsoon</TD><td>number of message board comments at comingsoon.net</td>
  </TR>
  <TR>
    <TD>fandango</TD><td>sum of “can't wait” and “don't care” votes at fandango.com</td>
  </TR>  
  <TR>
    <TD>cntwait3</TD><td>percent of “can't wait” votes at fandango.com</td>
  </TR>
</TABLE>

# DEVELOPMENT
We plot histograms for all the continuous variables - box, budget, starpwr to see if its distribution is skewed. In this case, box, and budget is skewed. So, we transformed these variables using log-transform. <br>
![image](https://github.com/tejus15/PCA/assets/78174194/606f619f-e659-4605-9b4d-dde23f4b4f97)

![image](https://github.com/tejus15/PCA/assets/78174194/6cd30046-34bf-4154-8e02-80dac6ce8009)

We performed OLS regression, the dependent variable is log10(box)  using all the independent variables (original form, not log-transformed), except the buzz variables - addict, cmngsoon, fandango, cntwait3. R-squared is 0.342 and Adjusted R-squared is 0.214. Based on t-statistics and associated probabilities (p > |t|) with significance level at 0.1, budget, sequel, and horror are significant. 

We then plotted the distribution of the buzz variables using a histogram and saw if any of them were skewed. These three variables' distribution were skewed - addict, cmngsoon, fandango. Applied log transform to handle the issue. 

![image](https://github.com/tejus15/PCA/assets/78174194/51ce4645-0b14-41a9-8a68-4c054ef5bcd2)

![image](https://github.com/tejus15/PCA/assets/78174194/874ec89d-d9d6-4e60-8e3d-eee05ecf2dd9)
We ran a linear regression of box office revenues on all the independent variables, including the “buzz” variables (transformed as needed). We found out that the R-squared is 0.624 and Adjusted R-squared is 0.512. Based on t-statistics and associated probabilities (p > |t|) with significance level at 0.1, <b>PG, action, animated, addict, and cntwait3 are significant</b>. 
<br>We then performed regression again, but this time only with the significant variables. R-squared is 0.558 and Adjusted R-squared is 0.519. Based on t-statistics and associated probabilities (p > |t|) with significance level at 0.1, <b>action, animated, addict, and cntwait3 are significant, but PG is not significant anymore</b>.

[(Back to top)](#table-of-contents)



 
 

 


 
 





 
 
 
