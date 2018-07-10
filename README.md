# policy-tree-and-alternate-views
An idea about how to handle custom composites

There are two excel files in this folder which illustrates a possible approach to defining composites.  

The starting point is a policy tree of portfolio structure (PolicyTree.xlsx) .  It has the following columns:
 - Asset_Class  (e.g. Equities)	
 - Portfolio (e.g. Domestic Equities)
 - Sub_portfolio (e.g. Large Cap)
 - Category (e.g. Megabuyout)
 - Fund_Name (a long name for a fund)
 - Fund_Id (short mnemonic name which is a unique identifier - e.g. Aplo7)
 - Sponsor (e.g. Blackstone)
 - SAA_Benchmark (the benchmark assigned for the asset class in the SAA)
 - Imp_Plan_Benchmark (the benchmark assigned in the implementation plan)
 - Quarter_Lagged (whether or not the benchmark is quarter lagged)

This file has a row for every public and private fund that shows where it stands in the policy portfolio structure.

The other file is an example of a possible alternate view in which you define one or more composites for analysis. 

The columns for the alternate view are:
 - Composite_Name (what to call the composite you are creating)
 - Exclude (if TRUE, then exclude the items described from the composite)
 - Asset_Class (same as policy tree, match all if blank)
 - Portfolio (same as policy tree, match all if blank)
 - Sub_Portfolio (same as policy tree, match all if blank)
 - Category (same as policy tree, match all if blank)
 - Fund_Id (same as policy tree, match all if blank)
 - Sponsor (same as policy tree, match all if blank)
 - Use_SAA (use the SAA benchmark if TRUE)
 - Use_Imp_Plan (use the implementation plan benchmark if TRUE)
 - Composite_Benchmark (use this benchmark if specified)

Note that only one of the last three columns should contain a value. 

I have filled out the PolicyTree with a partial specification of an equity including two each of private equity and public equity.  I have provided an example portfolio view specification called "AltView1.xlsx".  

AltView1 creates two special composities.  Equities_X_BX is the equities portfolio excluding Blackstone.  So, if you want to know is Blackstone adding value you look at the return on the Equities Asset_Class portfolio (defined in the PolicyTree) then compare it to a custom composite of equities excluding Blackstone.  If the return of the  custom composite is lower, then Blackstone added value.

Equities_Meg_Large is the other composite.  It is a composite of equities that either mega-buyout private or large cap public equities.  Note that because Sub_Portfolio is blank is line 4 it matches to both international and domestic large cap equities.

  


