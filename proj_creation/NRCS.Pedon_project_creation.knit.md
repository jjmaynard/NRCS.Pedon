
<!-- rnb-text-begin -->

---
title: "Creating R Projects"
output: html_notebook
---

Steps to create R projects:
1.	Navigate to directory that will host the project folder.
2.	In R, load ‘rrtools’ and ‘workflowr’
3.	Run ‘rrtools’ code to create research compendium:
a.	rrtools::use_compendium("myproject ")
b.	usethis::use_mit_license(name = "Jonathan J Maynard")
c.	usethis::use_git()
d.	Create github ‘repo’ token for “myproject”
e.	usethis::use_github(auth_token = "xxxx", protocol = "https", private = FALSE)
f.	rrtools::use_readme_rmd()
g.	rrtools::use_analysis()
h.	rename the ‘analysis’ folder to ‘report’
i.	rrtools::use_dockerfile()
j.	rrtools::use_travis()
4.	Run ‘workflowr’ code to create research website
a.	wflow_start("myproject_site")
b.	wflow_build() and wflow_view() to build and view website
c.	wflow_publish(c("analysis/index.Rmd", "analysis/about.Rmd", "analysis/license.Rmd"), "Publish the initial files for myproject")
d.	wflow_status() to check if docs have been published
5.	Integreate rrtools folder and workflow folder:
a.	Move items from "myproject_site" to "myproject "
6.	Commit changes with Git and push to GitHub. All future changes can be pushed to

# Modify this section for each new project

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYGBgclxuYGBgclxuIyBzZXQgcHJvamVjdCBuYW1lIGFuZCBwYXRoXG5uYW1lIDwtIFxcTFBLUy5HaGFuYVxcXG5wYXRoIDwtIFxcQzovUl9Ecml2ZS9EYXRhX0ZpbGVzL0xQS1NfRGF0YS9SX1Byb2plY3RzL0xQS1MuR2hhbmFcXFxuYGBgXG5gYGBcbmBgYCJ9 -->

```r
```r
```r
# set project name and path
name <- \LPKS.Ghana\
path <- \C:/R_Drive/Data_Files/LPKS_Data/R_Projects/LPKS.Ghana\
```
```
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiXHUwMDFiWzMybXZcdTAwMWJbMzltIFNldHRpbmcgYWN0aXZlIHByb2plY3QgdG8gXHUwMDFiWzM0bSdDOi9SX0RyaXZlL0RhdGFfRmlsZXMvTFBLU19EYXRhL1JfUHJvamVjdHMvTlJDUy5QZWRvbidcdTAwMWJbMzltXG5cdTAwMWJbMzJtdlx1MDAxYlszOW0gV3JpdGluZyBcdTAwMWJbMzRtJ0xJQ0VOU0UnXHUwMDFiWzM5bVxuXHUwMDFiWzMybXZcdTAwMWJbMzltIFdyaXRpbmcgXHUwMDFiWzM0bSdMSUNFTlNFLm1kJ1x1MDAxYlszOW1cblx1MDAxYlszMm12XHUwMDFiWzM5bSBBZGRpbmcgXHUwMDFiWzM0bSdeTElDRU5TRVxcXFwubWQkJ1x1MDAxYlszOW0gdG8gXHUwMDFiWzM0bSdwcm9qX2NyZWF0aW9uLy5SYnVpbGRpZ25vcmUnXHUwMDFiWzM5bVxuIn0= -->

```
[32mv[39m Setting active project to [34m'C:/R_Drive/Data_Files/LPKS_Data/R_Projects/NRCS.Pedon'[39m
[32mv[39m Writing [34m'LICENSE'[39m
[32mv[39m Writing [34m'LICENSE.md'[39m
[32mv[39m Adding [34m'^LICENSE\\.md$'[39m to [34m'proj_creation/.Rbuildignore'[39m
```



<!-- rnb-output-end -->

<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYGBgclxudXNldGhpczo6dXNlX2dpdCgpXG5gYGBcbmBgYCJ9 -->

```r
```r
usethis::use_git()
```
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiXHUwMDFiWzMybXZcdTAwMWJbMzltIEluaXRpYWxpc2luZyBHaXQgcmVwb1xuXHUwMDFiWzMybXZcdTAwMWJbMzltIEFkZGluZyBcdTAwMWJbMzRtJy5SaGlzdG9yeSdcdTAwMWJbMzltLCBcdTAwMWJbMzRtJy5SZGF0YSdcdTAwMWJbMzltLCBcdTAwMWJbMzRtJy5odHRyLW9hdXRoJ1x1MDAxYlszOW0sIFx1MDAxYlszNG0nLkRTX1N0b3JlJ1x1MDAxYlszOW0gdG8gXHUwMDFiWzM0bSdwcm9qX2NyZWF0aW9uLy5naXRpZ25vcmUnXHUwMDFiWzM5bVxuVGhlcmUgYXJlIDkgdW5jb21taXR0ZWQgZmlsZXM6XG4qIFx1MDAxYlszNG0ncHJval9jcmVhdGlvbi8uZ2l0aWdub3JlJ1x1MDAxYlszOW1cbiogXHUwMDFiWzM0bSdwcm9qX2NyZWF0aW9uLy5SYnVpbGRpZ25vcmUnXHUwMDFiWzM5bVxuKiBcdTAwMWJbMzRtJ3Byb2pfY3JlYXRpb24vLlJwcm9maWxlJ1x1MDAxYlszOW1cbiogXHUwMDFiWzM0bSdwcm9qX2NyZWF0aW9uL0RFU0NSSVBUSU9OJ1x1MDAxYlszOW1cbiogXHUwMDFiWzM0bSdwcm9qX2NyZWF0aW9uL0xJQ0VOU0UnXHUwMDFiWzM5bVxuKiBcdTAwMWJbMzRtJ3Byb2pfY3JlYXRpb24vTElDRU5TRS5tZCdcdTAwMWJbMzltXG4qIFx1MDAxYlszNG0ncHJval9jcmVhdGlvbi9OQU1FU1BBQ0UnXHUwMDFiWzM5bVxuKiBcdTAwMWJbMzRtJ3Byb2pfY3JlYXRpb24vTlJDUy5QZWRvbi5ScHJvaidcdTAwMWJbMzltXG4qIFx1MDAxYlszNG0ncHJval9jcmVhdGlvbi9wcm9qX2NyZWF0aW9uLydcdTAwMWJbMzltXG5JcyBpdCBvayB0byBjb21taXQgdGhlbT9cblxuMTogTm90IG5vd1xuMjogTmVnYXRpdmVcbjM6IEZvciBzdXJlXG4ifQ== -->

```
[32mv[39m Initialising Git repo
[32mv[39m Adding [34m'.Rhistory'[39m, [34m'.Rdata'[39m, [34m'.httr-oauth'[39m, [34m'.DS_Store'[39m to [34m'proj_creation/.gitignore'[39m
There are 9 uncommitted files:
* [34m'proj_creation/.gitignore'[39m
* [34m'proj_creation/.Rbuildignore'[39m
* [34m'proj_creation/.Rprofile'[39m
* [34m'proj_creation/DESCRIPTION'[39m
* [34m'proj_creation/LICENSE'[39m
* [34m'proj_creation/LICENSE.md'[39m
* [34m'proj_creation/NAMESPACE'[39m
* [34m'proj_creation/NRCS.Pedon.Rproj'[39m
* [34m'proj_creation/proj_creation/'[39m
Is it ok to commit them?

1: Not now
2: Negative
3: For sure
```



<!-- rnb-output-end -->

<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYGBgclxuM1xuYGBgXG5gYGAifQ== -->

```r
```r
3
```
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiXHUwMDFiWzMybXZcdTAwMWJbMzltIEFkZGluZyBmaWxlc1xuXHUwMDFiWzMybXZcdTAwMWJbMzltIE1ha2luZyBhIGNvbW1pdCB3aXRoIG1lc3NhZ2UgXHUwMDFiWzM0bSdJbml0aWFsIGNvbW1pdCdcdTAwMWJbMzltXG4ifQ== -->

```
[32mv[39m Adding files
[32mv[39m Making a commit with message [34m'Initial commit'[39m
```



<!-- rnb-output-end -->

<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYGBgclxuI0NyZWF0ZSBnaXRodWIgw6LigqzLnHJlcG/DouKCrOKEoiB0b2tlbiBmb3Igw6LigqzFk215cHJvamVjdMOi4oKswp1cbnVzZXRoaXM6OnVzZV9naXRodWIoYXV0aF90b2tlbiA9IFxcYjA2MDZhZTQxYzFhMjlkOTgxNDIxYWIyZTQxMDBlNDU5NTdjYjVlMFxcLCBwcm90b2NvbCA9IFxcaHR0cHNcXCwgcHJpdmF0ZSA9IEZBTFNFKVxuYGBgXG5gYGAifQ== -->

```r
```r
#Create github â€˜repoâ€™ token for â€œmyprojectâ€
usethis::use_github(auth_token = \b0606ae41c1a29d981421ab2e4100e45957cb5e0\, protocol = \https\, private = FALSE)
```
```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiVGhlIGBhdXRoX3Rva2VuYCBhcmd1bWVudCBvZiBgdXNlX2dpdGh1YigpYCBpcyBkZXByZWNhdGVkIGFzIG9mIHVzZXRoaXMgMi4wLjAuXG51c2V0aGlzIG5vdyBkZWxlZ2F0ZXMgdG9rZW4gbG9va3VwIHRvIHRoZSBnaCBwYWNrYWdlLCB3aGljaCByZXRyaWV2ZXMgY3JlZGVudGlhbHMgYmFzZWQgb24gdGhlIHRhcmdldGVkIGhvc3QgVVJMLlxuVGhpcyBVUkwgaXMgZGV0ZXJtaW5lZCBieSB0aGUgY3VycmVudCBwcm9qZWN0J3MgR2l0IHJlbW90ZXMuXG5UaGUgXHUwMDFiWzkwbWBhdXRoX3Rva2VuYFx1MDAxYlszOW0gYXJndW1lbnQgaXMgaWdub3JlZCBhbmQgd2lsbCBldmVudHVhbGx5IGJlIHJlbW92ZWQuXHUwMDFiWzMybXZcdTAwMWJbMzltIENoZWNraW5nIHRoYXQgY3VycmVudCBicmFuY2ggaXMgZGVmYXVsdCBicmFuY2ggKFx1MDAxYlszNG0nbWFzdGVyJ1x1MDAxYlszOW0pXG4ifQ== -->

```
The `auth_token` argument of `use_github()` is deprecated as of usethis 2.0.0.
usethis now delegates token lookup to the gh package, which retrieves credentials based on the targeted host URL.
This URL is determined by the current project's Git remotes.
The [90m`auth_token`[39m argument is ignored and will eventually be removed.[32mv[39m Checking that current branch is default branch ([34m'master'[39m)
```



<!-- rnb-output-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuYGBgclxuYGBgclxuI1J1biDDg8Kiw6LigJrCrMOLxZN3b3JrZmxvd3LDg8Kiw6LigJrCrMOi4oCewqIgY29kZSB0byBjcmVhdGUgcmVzZWFyY2ggd2Vic2l0ZVxud2Zsb3dfc3RhcnQod2Zscl9wYXRoLCBnaXQgPSBGQUxTRSlcbndmbG93X2J1aWxkKCkgI3RvIGJ1aWxkICB3ZWJzaXRlXG53Zmxvd192aWV3KCkgICN2aWV3IHdlYnNpdGVcbmBgYFxuYGBgXG5gYGAifQ== -->

```r
```r
```r
#Run Ã¢â‚¬ËœworkflowrÃ¢â‚¬â„¢ code to create research website
wflow_start(wflr_path, git = FALSE)
wflow_build() #to build  website
wflow_view()  #view website
```
```
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxubGlicmFyeShycnRvb2xzKVxubGlicmFyeSh3b3JrZmxvd3IpXG5gYGAifQ== -->

```r
library(rrtools)
library(workflowr)
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


# Add auth_token for project


<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuI0NyZWF0ZSBnaXRodWIg4oCYcmVwb+KAmSB0b2tlbiBmb3Ig4oCcbXlwcm9qZWN04oCdXG51c2V0aGlzOjp1c2VfZ2l0aHViKHByb3RvY29sID0gXCJodHRwc1wiLCBwcml2YXRlID0gRkFMU0UpXG5cbmBgYCJ9 -->

```r
#Create github ‘repo’ token for “myproject”
usethis::use_github(protocol = "https", private = FALSE)

```

<!-- rnb-source-end -->

<!-- rnb-output-begin eyJkYXRhIjoiXHUwMDFiWzMybXZcdTAwMWJbMzltIFNldHRpbmcgYWN0aXZlIHByb2plY3QgdG8gXHUwMDFiWzM0bSdDOi9SX0RyaXZlL0RhdGFfRmlsZXMvTFBLU19EYXRhL1JfUHJvamVjdHMvTlJDUy5QZWRvbidcdTAwMWJbMzltXG5cdTAwMWJbMzJtdlx1MDAxYlszOW0gQ2hlY2tpbmcgdGhhdCBjdXJyZW50IGJyYW5jaCBpcyBkZWZhdWx0IGJyYW5jaCAoXHUwMDFiWzM0bSdtYXN0ZXInXHUwMDFiWzM5bSlcbiJ9 -->

```
[32mv[39m Setting active project to [34m'C:/R_Drive/Data_Files/LPKS_Data/R_Projects/NRCS.Pedon'[39m
[32mv[39m Checking that current branch is default branch ([34m'master'[39m)
```



<!-- rnb-output-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


# Run workflowr code as chunk

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuI1J1biDigJh3b3JrZmxvd3LigJkgY29kZSB0byBjcmVhdGUgcmVzZWFyY2ggd2Vic2l0ZVxud2Zsb3dfc3RhcnQod2Zscl9wYXRoLCBnaXQgPSBGQUxTRSlcbndmbG93X2J1aWxkKCkgI3RvIGJ1aWxkICB3ZWJzaXRlXG53Zmxvd192aWV3KCkgICN2aWV3IHdlYnNpdGVcbmBgYCJ9 -->

```r
#Run ‘workflowr’ code to create research website
wflow_start(wflr_path, git = FALSE)
wflow_build() #to build  website
wflow_view()  #view website
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


# Perform these steps
  1. rename "analysis/about.Rmd" to "analysis/code.Rmd"
  2. create new Rmarkdown file "analysis/data.Rmd"

# Run workflowr code as chunk

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuc2V0d2Qod2Zscl9wYXRoKVxud2Zsb3dfcHVibGlzaChjKFwiYW5hbHlzaXMvaW5kZXguUm1kXCIsIFwiYW5hbHlzaXMvY29kZS5SbWRcIiwgXCJhbmFseXNpcy9kYXRhLlJtZFwiLCBcImFuYWx5c2lzL2xpY2Vuc2UuUm1kXCIpLCBcIlB1Ymxpc2ggdGhlIGluaXRpYWwgZmlsZXMgZm9yIG15cHJvamVjdFwiKVxud2Zsb3dfc3RhdHVzKCkgI3RvIGNoZWNrIGlmIGRvY3MgaGF2ZSBiZWVuIHB1Ymxpc2hlZFxuYGBgIn0= -->

```r
setwd(wflr_path)
wflow_publish(c("analysis/index.Rmd", "analysis/code.Rmd", "analysis/data.Rmd", "analysis/license.Rmd"), "Publish the initial files for myproject")
wflow_status() #to check if docs have been published
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->


#Integreate rrtools folder and workflowr folder:
Changes to rrtools folder (project folder):
  1. erase rrtools .gitignore and .profile
  2. rename analysis folder to 'results'
  3. move results/data files to data/
  4. erase R/ folder
  5. Create 'proj_setup' folder and save Project_creation.Rmd script in this folder
  6. move README.md in /output folder to data/derived/ and erase /output

Changes to workflowr folder (sub project folder):
  1. erase workflowr README.Rmd
  2. move README.Rmd in data folder to rrtools data folder and erase data folder
  3. erase workflowr Rproj file
  4. move all files from workflowr folder to main project folder, then erase workflowr folder
  5. add 'proj_setup/' to .gitignore

Commit changes with Git and push to GitHub.
In Github, set github project site to /docs in settings




<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuc2V0d2QocGF0aClcbndmbG93X3B1Ymxpc2goYyhcImFuYWx5c2lzL2luZGV4LlJtZFwiLCBcImFuYWx5c2lzL2NvZGUuUm1kXCIsIFwiYW5hbHlzaXMvZGF0YS5SbWRcIiwgXCJhbmFseXNpcy9saWNlbnNlLlJtZFwiKSwgXCJQdWJsaXNoIHRoZSBpbml0aWFsIGZpbGVzIGZvciBteXByb2plY3RcIilcbndmbG93X3N0YXR1cygpICN0byBjaGVjayBpZiBkb2NzIGhhdmUgYmVlbiBwdWJsaXNoZWRcbmBgYCJ9 -->

```r
setwd(path)
wflow_publish(c("analysis/index.Rmd", "analysis/code.Rmd", "analysis/data.Rmd", "analysis/license.Rmd"), "Publish the initial files for myproject")
wflow_status() #to check if docs have been published
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



##Examples for making changes to project website with workflowr

<!-- rnb-text-end -->


<!-- rnb-chunk-begin -->


<!-- rnb-source-begin eyJkYXRhIjoiYGBgclxuI0NoZWNrIGlmIGFueSBkb2NzIGhhdmUgbm90IHlldCBiZWVuIHB1Ymxpc2hlZFxud2Zsb3dfc3RhdHVzKCkgXG4jIHNpbmdsZSBmaWxlXG53Zmxvd19wdWJsaXNoKFwiYW5hbHlzaXMvZmlsZS5SbWRcIiwgXCJJbmZvcm1hdGl2ZSBjb21taXQgbWVzc2FnZVwiKVxuIyBBbGwgdHJhY2tlZCBmaWxlcyB0aGF0IGhhdmUgYmVlbiBlZGl0ZWRcbndmbG93X3B1Ymxpc2goYWxsID0gVFJVRSwgbWVzc2FnZSA9IFwiSW5mb3JtYXRpdmUgY29tbWl0IG1lc3NhZ2VcIilcbiMgQSBuZXcgZmlsZSBwbHVzIGFsbCB0cmFja2VkIGZpbGVzIHRoYXQgaGF2ZSBiZWVuIGVkaXRlZFxud2Zsb3dfcHVibGlzaChcImFuYWx5c2lzL2ZpbGUuUm1kXCIsIFwiSW5mb3JtYXRpdmUgY29tbWl0IG1lc3NhZ2VcIiwgYWxsID0gVFJVRSlcbiMgTXVsdGlwbGUgZmlsZXNcbndmbG93X3B1Ymxpc2goYyhcImFuYWx5c2lzL2ZpbGUuUm1kXCIsIFwiYW5hbHlzaXMvYW5vdGhlci5SbWRcIiksXG4gICAgICAgICAgICAgIFwiSW5mb3JtYXRpdmUgY29tbWl0IG1lc3NhZ2VcIilcbiMgQWxsIFIgTWFya2Rvd24gZmlsZXMgdGhhdCBzdGFydCB3aXRoIHRoZSBwYXR0ZXJuIFwibmV3X1wiXG53Zmxvd19wdWJsaXNoKFwiYW5hbHlzaXMvbmV3XypSbWRcIiwgXCJJbmZvcm1hdGl2ZSBjb21taXQgbWVzc2FnZVwiKVxuIyBSZXB1Ymxpc2ggYWxsIHB1Ymxpc2hlZCBmaWxlcyBldmVuIHRob3VnaCB0aGV5IGhhdmVuJ3QgYmVlbiBtb2RpZmllZC5cbiMgVXNlZnVsIGZvciBjaGFuZ2luZyBzb21lIHVuaXZlcnNhbCBhc3BlY3Qgb2YgdGhlIHNpdGUsIGUuZy4gdGhlIHRoZW1lXG4jIHNwZWNpZmllZCBpbiBfc2l0ZS55bWwuXG53Zmxvd19wdWJsaXNoKFwiYW5hbHlzaXMvX3NpdGUueW1sXCIsIFwic2l0ZSB1cGRhdGVcIiwgcmVwdWJsaXNoID0gVFJVRSlcbiMgUHVibGlzaCBhbGwgcHJldmlvdXNseSBwdWJsaXNoZWQgZmlsZXMgdGhhdCBoYXZlIGJlZW4gY29tbWl0dGVkIG1vcmVcbiMgcmVjZW50bHkgdGhhbiB0aGVpciBjb3JyZXNwb25kaW5nIEhUTUwgZmlsZXMuIFRoaXMgaXMgdXNlZnVsIGlmIHlvdSBsaWtlIHRvXG4jIG1hbnVhbGx5IGNvbW1pdCB5b3VyIFIgTWFya2Rvd24gZmlsZXMuXG53Zmxvd19wdWJsaXNoKHVwZGF0ZSA9IFRSVUUpXG5cbndmbG93X3B1Ymxpc2goXCJhbmFseXNpcy9pbmRleC5SbWRcIiwgYWxsID0gVFJVRSwgbWVzc2FnZSA9IFwiVXBkYXRlIGluZGV4XCIpXG53Zmxvd19wdWJsaXNoKFwiYW5hbHlzaXMvRVNHX0NvdmFyaWF0ZV9Qcm9jZXNzaW5nLlJtZFwiLCBhbGwgPSBUUlVFLCBtZXNzYWdlID0gXCJVcGRhdGUgRVNHIGNvdmFyaWF0ZSBwcm9jZXNzaW5nXCIpXG5gYGAifQ== -->

```r
#Check if any docs have not yet been published
wflow_status() 
# single file
wflow_publish("analysis/file.Rmd", "Informative commit message")
# All tracked files that have been edited
wflow_publish(all = TRUE, message = "Informative commit message")
# A new file plus all tracked files that have been edited
wflow_publish("analysis/file.Rmd", "Informative commit message", all = TRUE)
# Multiple files
wflow_publish(c("analysis/file.Rmd", "analysis/another.Rmd"),
              "Informative commit message")
# All R Markdown files that start with the pattern "new_"
wflow_publish("analysis/new_*Rmd", "Informative commit message")
# Republish all published files even though they haven't been modified.
# Useful for changing some universal aspect of the site, e.g. the theme
# specified in _site.yml.
wflow_publish("analysis/_site.yml", "site update", republish = TRUE)
# Publish all previously published files that have been committed more
# recently than their corresponding HTML files. This is useful if you like to
# manually commit your R Markdown files.
wflow_publish(update = TRUE)

wflow_publish("analysis/index.Rmd", all = TRUE, message = "Update index")
wflow_publish("analysis/ESG_Covariate_Processing.Rmd", all = TRUE, message = "Update ESG covariate processing")
```

<!-- rnb-source-end -->

<!-- rnb-chunk-end -->


<!-- rnb-text-begin -->



<!-- rnb-text-end -->

