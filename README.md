# Australian digital transformation without the Authority

It has been another disappointing year for the Australian tech community, and I feel that we need a new strategy.   

Taiwan’s Sunflower movement opened in 2014 when the pro-unification Kuomintang Party signed a secret “Service and Trade agreement” with the Chinese Communist Party, and a group of Taiwanese students and technologists stormed the parliament and stopped them ratifying it.  Since then, it has developed into a wonderful [example of how democracy and technology fit together](https://g0v.tw/manifesto/en/). They build software that strengthens their democracy, improves human rights, and actively involves citizens in decisions so they can [“live democracy day by day.”](https://twitter.com/audreyt/status/1309396603652902912?s=20) 

Here in Aus, the complete exclusion of Australians with technical knowledge from decisionmaking and development of public technology is so normalised that the minister in charge of digital transformation can get away with describing as a “sovereign Australian app” a system that was ported from Singaporean code, improved with some tricks from the UK, uses completely secret server-side algorithms probably from the Boston Consulting Group, stores detailed information about Australians on the Amazon cloud, and didn’t work when Australians needed it.

I do not have a complete plan for turning things around, but this situation has to change, and those of us who understand technology are the ones who have to change it. 

Inspired by Taiwan’s Sunflower movement, I want to start thinking about how we could get an Australian knock-off started. This essay is an opinionated list of my preferred priorities, biased towards the projects I already know and care about – please join the discussion and add your own alternatives and plans.

## Covidsafe is bad, but it’s not unusual

First a little background about COVIDSafe.  Based on Singapore’s Tracetogether (now abandoned), with some imported tricks from the UK’s (now abandoned) centralised contact tracing app, the COVIDSafe app attempts to gather lists of contacts via bluetooth, which can be uploaded to a server for processing and notification if the person tests positive for COVID19.  Since its release in April, COVIDSafe has suffered from numerous privacy and functionality problems, many of which have been [identified by the tech community](https://github.com/vteague/contactTracing/blob/master/blog/2020-07-07IssueSummary.md) and hence corrected by the authorities.  Unfortunately, just as the app code was reaching a stage where most of its functionality seemed to be about as good as could be expected, the DTA decided to start again with a new Bluetooth communication layer called Herald.  There is no clear evidence about whether Herald improved or downgraded functionality, but it certainly re-introduced a number of the privacy and interference problems that had been corrected.

We are well past the number of free hours of work from the Australian tech community that could have been spent successfully completing an app that works on the Google/Apple Exposure Notification system.

If you are one of the many people who gave up their spare time to find and fix bugs in COVIDSafe, only to find them re-introduced by the Herald update, then I am really sorry.  That is not how this is supposed to go. You have still performed an important role by telling people the truth about the technology, which matters to ordinary people’s decisions about using it.  Ironically, by making calm and careful technical analyses of the system and helpfully suggesting corrections, we won the propaganda war (https://twitter.com/Lizzie_OShea/status/1257185135478226945).

But the important point is this: **Not one thing that has dismayed the tech community about COVIDSafe is unique to COVIDSafe.** 

Rejection of superior technology to select an inferior design for political reasons?  Consider the [Trusted Digital Identity Framework’s](https://www.dta.gov.au/our-projects/digital-identity/trusted-digital-identity-framework) rejection of a public key infrastructure.  Lying to Parliament?  When an official from the commonwealth Department of Health was [asked by a Senate committee about the easy re-identification of Medicare-PBS data published by her department](https://t.co/cdzlOJVRrT?amp=1), she denied it was easily re-identifiable and admitted only that “it was asserted to be possible to access some very limited encryption,” despite re-identification being a [simple matter of basic database querying that had nothing to do with encryption](https://arxiv.org/abs/1712.05627).  [Dismissing concerns](https://www.abc.net.au/news/2018-08-14/voters-in-act-election-could-have-ballot-choices-identified/10115670) even after they were conclusively demonstrated? [Misleading users?](https://www.elections.nsw.gov.au/About-us/Media-centre/News-media-releases/NSW-Electoral-Commission-iVote-and-Swiss-Post) Pressuring a university into silencing open discussion of its flaws? None of these are COVIDSafe-related innovations.

Not even the decision to throw out months of free expert labour and corrected bugs, and start again from scratch, is unique to COVIDSafe. Elections ACT did exactly the same thing this year, replacing an open-source version of their counting code that had been extensively reviewed and corrected, with a hastily-implemented [buggy version](https://github.com/SiliconEconometrics/PublicService/blob/master/CountVotes/2020%20Errors%20In%20ACT%20Counting.pdf) just before the election.

If anything, COVIDSafe is a little more transparent than other comparable projects and, therefore, probably less incompetent than the ones we cannot see. Most of the bug-fixes were actioned, not counting those reintroduced by Herald.  When Ben Frengley and I found a [code proxying attack on the myGovID system](https://thinkingcybersecurity.com/DigitalID/), the ATO characterised it as a “user education problem” and still refuses to fix it.

## Does it have to be this way?

There is nothing natural or universal about the exclusion of people with technical knowledge from decisions about - and development of - government tech.  

In Switzerland, when we discovered [a serious cryptographic problem in their e-voting system](https://openprivacy.ca/assets/how-not-to-prove-your-election-outcome-preprint.pdf), the Federal Chancellery funded us and Swiss experts to collaborate on an [open, in-depth reassessment of the entire program](https://www.bk.admin.ch/bk/en/home/politische-rechte/e-voting/berichte-und-studien.html).  The NSW iVote system had the same bugs, but there was no serious reassessment and there is no plan to change their approach.

In Taiwan, the technologists who started the Sunflower movement were invited in to government.

The community that has grown up around the public examination of COVIDSafe can be a catalyst for better technology policy and practice across Australia’s public sector.  I am delighted that a community of geeks is suddenly outraged by the things that I had given up hope of changing.  After years of wondering why nobody else seemed to care, a whole community of people want change. 

First, my most-urgent legislative change.

## Legislation/politics: democracy is the thing we must not sacrifice

We can see COVIDSafe’s app code and identify mistakes.  We can download the myGovID app and examine its behaviour.  But years of effort by democracy activists and [even a Senate motion](https://www.smh.com.au/technology/government-rejects-senate-order-to-disclose-electoral-commission-software-code-20140716-zti03.html) have failed to bring any details about the Senate scanning and counting code to light.  Before you say, “Never mind, that code only chooses our Senators, why should I care about its security or correctness?” consider that (as far as I can tell) it is supplied entirely by foreign companies, Fuji-Xerox and [Scytl](https://www.tenders.gov.au/Cn/Show/471f2731-fa2f-e235-5e5d-91fb7b9a53c1), and (as far as I know) has never had any independent review by anyone with any knowledge of election verification.

I believe the highest priority for technically-informed legislative change is to mandate an audit of the digitised preferences against the paper Senate ballots.

Please add your preferred priorities to the Discussion-legislation/politics tab here. 

## Communication: first, people have to care

Some of the best successes have been the simplest. NotMyDebt wasn’t just a hashtag – it was also a [highly effective program for aggregating stories](https://www.notmydebt.com.au/) from those who had been unjustly accused of owing money.  The combination of effective communication and useful tech made for a [historic win](https://www.sbs.com.au/news/federal-government-settles-1-2-billion-class-action-over-its-unlawful-robodebt-scheme).

One of the most effective tools for supporting Australian democracy is [righttoknow.org.au](https://www.righttoknow.org.au/), which provides a simple public interface for Freedom of Information requests.  It doesn’t let you do anything you couldn’t already do, yet their advice, support, coordination, and publication is tremendously powerful.

Digital Rights Watch, Electronic Frontiers Australia and AccessNow all do a wonderful job of communication to both ordinary people and decisionmakers. We should always work hard to inform formal democratic processes.

However, I think we made a mistake by working only through the official “consultation” process on issues such as TOLA, the anti-encryption legislation passed in 2018, and the various followups that undermine Australian security and privacy further.  We need to think about how to make technically-literate protest visible and appealing to non-geeks. What would a security-and-privacy version of the climate protests or black lives matter protests look like? Who would join us? How would we invite them in? Conversely, what technology would support democratic expression on those other issues?

Please add your ideas for better coordination and communication to the Discussion – communication tab.

## Outside-government public technology 

We are the people who know how to build things.  

I know of lots of Australians - both inside and outside government - building valuable technology that supports Australian democracy.  [Michelle Blom’s election auditing software](https://github.com/michelleblom), specifically designed for Australian-style preferential elections, has been used in San Francisco but not (yet) here.  Australian open-source implementations of [STV](https://github.com/siliconeconometrics/publicservice) [counting](https://github.com/grahame/dividebatur) software could be used immediately instead of the often-secret, often-foreign code many of our electoral commissions use. 
Flux’s has a terrific [sub-project on encoding legislation](https://github.com/OpenGovAus/Aus-Bills).

So many other good things have been, are being, or could be built by the open source community without needing official endorsement.

Please add your ideas (or existing projects) to the Discussion – outside government technology tab.

## It doesn’t have to be this way

Nothing about COVIDSafe surprises me except the active involvement of a wonderful community of interested independent people.

I do not have a complete solution, but I hope this site can become a forum for focusing discussion on a better way our country can build public-sector technology.

```
that whenever people feel anger, they no longer turn their anger into helplessness, but rather into social outrage, which is an impulse for co-creation, and so my main suggestion is not to take this personal[ly], but take it social.
```
--- [Audrey Tang](https://twitter.com/audreyt/status/1309396582081544192)
