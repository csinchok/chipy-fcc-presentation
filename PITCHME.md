# Tracking Bots with Python 

Chris Sinchok

---

## Who am I?

- Not a data scientist |

- Pretty much just a web developer |

- Boy howdy, I am bad at pandas |

---

## DISCLAIMERS

- This data is messy |

- I will be hand-waving some complexities |

- My data isn't fully up-to-date |

- Would love to answer questions after, if you'd like to know more |

---

## What happened

- I analyzed comments on an FCC proposal |

- Found some weird patterns, and published a blog post about it |

- The post ended up getting quite a bit of traction |

---

## A short description of the issue

- The head of the FCC wants to roll back Title II regulations |

- Most tech people do not support this |

- Most ISPs would very much like this proposal to succeed |

---

## Public Comments?

- Any time the FCC has a proposal, they solicit public comments |

- Comments are not an actual vote |

- Public sentiment has swayed things before |

---

## My initial goals

- Get an idea of the overall public sentiment |

- Look at how much John Oliver changed the numbers |

- Build a website to provide an analysis of the data |

---

## The FCC has a Comment API!

- Returns JSON |

- With an API key, allows posting of comments |

- Drives the ECFS frontend |

---

# Let's look at the JSON!

---?code=my-comment.json&lang=json

@[2](Every comment has a unique ID)
@[19-25](Address isn't required, but it's often present)
@[26](Email isn't visible on the web frontend, but it's available in the API)
@[35-36](These dates are effectively the same--they're the time I made the comment)
@[37](This is the date the comment was approved and posted to the website)
@[99](The comment itself)

---

## My Toolset

- Started with Jupyter |

- Moved to an Elasticsearch backend |

- Analyzed the data with some Python scripts, storing the results in ES |

- Used a Kibana frontend for easy data viewing |

---

## First results

- There was an obvious "John Oliver" bump |

- There were a lot of duplicate text entries |

- The "John Oliver" comments were pretty easy to tag, but weren't identical |

---

## Tagging

- Grouping by "form letter" |

- Was there a full physical address? |

- Where did the comment come from? (Web, CSV, API) |

---

# Group #1: "Unprecedented"

+++

> The unprecedented regulatory power the Obama Administration imposed on the internet is smothering innovation, damaging the American economy and obstructing job creation. I urge the Federal Communications Commission to end the bureaucratic regulatory overreach of the internet known as Title II and restore the bipartisan light-touch regulatory consensus that enabled the internet to flourish for more than 20 years. The plan currently under consideration at the FCC to repeal Obama's Title II power grab is a positive step forward and will help to promote a truly free and open internet for everyone.

+++

## Commonalities

- Duplicate text |

- Real people, real addresses, real emails |

- Email in ALL CAPS |

- Submitted over the API |

+++

## Comment Rates

![Comment Rates](images/unprecedented-rates.png)

+++

---

# Group #2: "Free our internet"

+++

> In 2015, President Obama's FCC passed rules treating the Internet as a government regulated public utility for the first time in history. Those pushing hardest for the new rules were Silicon Valley monopolies like Google and leftist globalists like George Soros.
>
> Google in fact visited the White House more than 427 times during the Obama years. Leftist foundations like Soros' Open Society and the Ford Foundation spent almost $200 million pushing for the rule change.
>
> Now we know why. In less than two years big tech and their liberal allies have taken total control of our information and communications platforms. They have used their power to flatten competitors, ban speech, censor content, routinely violate our privacy, and silence dissenting voices.
>
> While Obama's goal clearly benefited radical progressives, leftist political candidates, and his Silicon Valley corporate cronies it destroyed the free and open Internet by establishing them as our information gatekeepers.
>
> I strongly encourage the FCC to oppose efforts by the TechLeft and liberal globalists to take over our Internet. Please roll back President Obama's disastrous rules immediately. The future of a free and open Internet is at stake.

+++

## Commonalities

- Duplicate text |

- Full addresses |

- Emails provided |

- Submitted via CSV in huge groupings |

---

# Group #3 "Taxpayers Protection Alliance"

+++

> Obama's Federal Communications Commission (FCC) forced regulations on the internet that put the government, and unaccountable bureaucrats, in control. These rules have cost taxpayers, slowed down broadband infrastructure investment, and hindered competition and choice for Americans. The time to remove the regulatory stranglehold on the internet is NOW. I urge the taxpayer-funded FCC to undo the terrible regulatory burdens that ex-FCC Chairman Tom Wheeler imposed on the internet. After 20 years, and trillions of dollars in infrastructure investment, there is no reason for the government to come in and ruin what has been a thriving tool that has changed the way we all live. Chairman Pai's proposal to repeal Title II regulations will ensure the continued growth of a dynamic, open internet for all American consumers and taxpayers.

+++

## Commonalities

- Duplicate text |

- Full addresses |

- Emails provided |

- Submitted via CSV in huge groupings |

+++

![Comment Rates](images/csv-rates.png)

---

# Why do I think these are bots?

+++

## The comment rates are...suspicious

+++

## The data is too good

- The addresses are full, and well formatted |

- No obviously fake emails, addresses |

- No one submitting twice |

+++

## There are a lot of "breached" accounts

- "Unprecedented": 67.4%
- "Free Our Internet": 74.2%
- "Outraged": 64.2%
- "Battle for the Net": 33.5%
- "John Oliver Viewers": 20.5%
- Control Sample: 31.5%

+++

## These aren't "visible" campaigns

- These aren't organizations with a ton of twitter followers |

- They aren't obviously getting traction online |

- For some of these, no one knows where the form lives |

+++

## We asked a bunch of the submitters

![Comment Rates](images/email-sample.png)

+++

## Survey Results

<table>
    <th>
        <td>Source</td>
        <td>I'm Unsure</td>
        <td>No</td>
        <td>Yes</td>
        <td>Sample Size</td>
        <td>Response Rate</td>
    </th>
    <tr>
        <td>battleforthenet</td>
        <td>2</td>
        <td>0</td>
        <td>29</td>
        <td>100</td>
        <td>31.0%</td>
    </tr>
</table>
