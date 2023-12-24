We have a 3rd party lead generator. We pay when lead reaches the following status: Lead status = Converted or Lead status = Retainer Received or ROSU (Referred out, Signed up) = 1

Our CFO needs the billing summed by venue, litigation/casetype, and month.
The amount we pay is based on the litigation and some specific casetypes:

personal injury (default) = 1000
elmiron = 2400
tmobile data breach = 20
Philips CPAP = 500
workers comp = 250
sunscreen = 1000
paraquat = 2000
social security = 100

Our attribution was incorrectly tracked until Sep 1st of 2021. Before this date, we were manually matching phone numbers that came through their system to calls that we received and paying for all converted leads from those numbers. Starting Sep 1st, we have our attribution correct, so we stopped paying for all leads and only the ones that came from Ask.Law.

One of our concerns is that a potential client may have filled out a form on the AskLaw website and then called to complete the consultation. This means that their record will show up twice in our dataset. We need to clean the duplicates from our data so we don't pay twice for these leads.

In joining the CTEs for our baseline intakes (based on marketing source and subsource) with our CTEs that are based on pulling records based on incoming phone number, we have to be careful about how we drop duplicates. In this table we don't have phone numbers. But because we may have them in the actual dashboard we need to be sure that we drop duplicates on the specific column that will drop any subsequent intake record generated - regardless of whether that row has a phone number associated or not.

Our tasks, therefore:

    remove dupes
    filter for converted leads
    filter for post-Aug leads
    add value column for lit/casetype
    output a pretty pivot table for the CFO


