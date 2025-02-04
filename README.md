
<!-- README.md is generated from README.Rmd. Please edit that file -->

# clinicalfd (Clinical Fake Data)

<!-- badges: start -->

<!-- badges: end -->

The goal of clinicalfd is to create Fake SDTM/ADaM data for generating
TFL.This data is available at
(<https://github.com/phuse-org/phuse-scripts>) for free to download for
public use see the licence here
(<https://github.com/phuse-org/phuse-scripts/blob/master/LICENSE.md>)

## Installation

You can install the released version of clinicalfd (clinical fake data)
from \[Github\] (<https://github.com/sas2r/clinical_fd>)

General Instructions:

Make sure you have lateset version of R-language , the way to check is
type in  
session() in R console .

If it \<= 0.4.7 then the Package may not be loaded, you need to have \>=
0.4.7.

To update the R-version

If R studio is on your Personnel drive then do Install.packages
(“rlang”) , then library (rlang) , check sessionInfo ()

NOTE: If you are using Rstudio on cloud this would not work , On R-cloud
simply go to right most corner of the window and change the R version to
either 4.0 or 4.1.

Once you have updated the R-languge then

<B>NOTE: devtools and clinical\_fd would install couple of standard
packages and would take some time

install.packages(“devtools”) wait for the dev tools to be installed then
call the library(devtools). Once the devtools is installed then you can
call install\_github(“sas2r/clinical\_fd”) to install the package
clinical\_fd (all lower case , with the underscore in it ) then call
library(clincalfd) (without the underscore)

During the process of Installation ( May take around 10 min depending on
the System) you will see couple of packages either been downloaded or
updated.

NOTE: Make sure you type in exactly as shown below without \# for
install packages part </B>

``` r
#install.packages("devtools") 

library(devtools)
#> Loading required package: usethis

#install_github("sas2r/clinical_fd")

library(clinicalfd)
## basic example code
```

(Please see dataguide in man folder for more information ) Where to Find
Key Data

Demographics and Populations

The ADSL (Subject Level Analysis Data) dataset contains all
subject-level variables for demographics, subject characteristics, and
population flags. Safety Key safety data are found in the datasets ADAE
(Adverse Events Analysis Data), ADLBC (Laboratory Results Chemistry
Analysis Data), ADLBH (Laboratory Results Hematology Analysis Data),
ADLBHY (Laboratory Results Hy’s Rule Analysis Data), and ADVS (Vital
Signs Analysis Dataset). In addition, ADTTE is specifically for safety
analyses of the time to the first dermatologic AE. Dermatologic AEs are
considered an adverse event of special interest.

Efficacy Study CDISCPilot01 has two primary endpoints, the Alzheimer’s
Disease Assessment Scale - Cognitive Subscale, total of 11 items
\[ADAS-Cog (11)\] at Week 24 and the Video-referenced Clinician’s
Interview-based Impression of Change (CIBIC+) at Week 24. All ADAS-Cog
data, including the first primary endpoint, can be found in the dataset
ADQSADAS. All CIBIC+ data, including the second primary endpoint, can be
found in the dataset ADQSCIBC. Mean Revised Neuropsychiatric Inventory
(NPI-X) data are considered secondary. These data can be found in the
dataset ADQSNPIX.

List of ADaM/SDTM Data sets available in ‘clinicalfd’ package are:

ADaM: adadas  
adae  
adcibc  
adlbc  
adlbcpv  
adlbh  
adlbhpv  
adlbhy  
adnpix  
adsl  
adtte  
advs

SDTM: ae  
cm  
dm  
ds  
ex  
lbch  
lbhe  
mh  
qsco  
qsda  
qsgi  
qshi  
relrec  
sc  
se  
suppae  
suppdm  
suppds  
supplbch  
supplbur  
sv  
ta  
te  
ti  
ts  
tv  
vs

## Example

This is a basic example which shows you how to solve a common problem:

``` r
#from SDTM
summary(dplyr::select(dm, age, sex , race, ethnic))
#>       age        sex                                   race    
#>  Min.   :50.00   F:179   AMERICAN INDIAN OR ALASKA NATIVE:  2  
#>  1st Qu.:70.25   M:127   ASIAN                           :  2  
#>  Median :77.00           BLACK OR AFRICAN AMERICAN       : 29  
#>  Mean   :75.09           WHITE                           :273  
#>  3rd Qu.:81.00                                                 
#>  Max.   :89.00                                                 
#>                     ethnic   
#>  HISPANIC OR LATINO    : 17  
#>  NOT HISPANIC OR LATINO:289  
#>                              
#>                              
#>                              
#> 
#from ADaM
summary(dplyr::select(adsl, age, sex , race, ethnic))
#>       age        sex                                   race    
#>  Min.   :51.00   F:143   AMERICAN INDIAN OR ALASKA NATIVE:  1  
#>  1st Qu.:70.00   M:111   BLACK OR AFRICAN AMERICAN       : 23  
#>  Median :77.00           WHITE                           :230  
#>  Mean   :75.09                                                 
#>  3rd Qu.:81.00                                                 
#>  Max.   :89.00                                                 
#>                     ethnic   
#>  HISPANIC OR LATINO    : 12  
#>  NOT HISPANIC OR LATINO:242  
#>                              
#>                              
#>                              
#> 
```

You can also embed plots, for example:

``` r
plot(dplyr::select(dm , sex, age) )
```

<img src="man/figures/README-gender-1.png" width="100%" />

What is special about using `README.Rmd` instead of just `README.md`?
You can include R chunks like so:

You’ll still need to render `README.Rmd` regularly, to keep `README.md`
up-to-date.

In that case, don’t forget to commit and push the resulting figure
files, so they display on GitHub\!
