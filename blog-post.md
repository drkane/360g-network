# Which funders make grants to the same recipients?

One great thing about grantmakers publishing data about who they fund
in the 360 Giving standard is that we can start to explore the network
of grants. 

One way of doing this is to look at how many recipients have received
funding from two different funders. A great way of visualising this
is through a chord diagram - I've used the fantastic 
[Flourish](https://app.flourish.studio/@flourish/chord-diagram)
tool to create this.

<iframe src='https://public.flourish.studio/visualisation/155633/embed' frameborder='0' scrolling='no' style='width:100%;height:600px;'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/155633/?utm_source=embed&utm_campaign=visualisation/155633' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>

The steps for doing this are:

1. Download the data we need from [GrantNav](http://grantnav.threesixtygiving.org/) - 
I've filtered this list to include all the grants in GrantNav for 2017.
There are 31,300 grants in this dataset.
2. Create a list of all combinations of recipient and funder. This means that 
where a recipient has received more than one grant from a funder they only have 
one row in the table.
3. Filter this list to remove any recipients that only received funding from
one funder. This filters the 24,976 unique recipients to 2,316 that have
received grants from more than one funder in the period.
4. Reshape the data table so the we have a list of the funders showing how
many recipients they have in common with other funders. This forms the input
to the chord diagram.

To do this data preparation I've used the Python programming language, and the
[pandas](https://pandas.pydata.org/) data analysis library. You can see the
code used to produce the source data in a [python notebook](/Prepare chord diagram.ipynb).

This kind of analysis is only possible when grantmakers use consistent
identifiers for the organisations they fund. By using a common identifier
(like a charity or company number) to identify the organisations they fund,
it's possible to compare these organisations across data published by
different funders. 
