# Tracking Bots with Python 

Chris Sinchok

---

## Who am I?

- Not a data scientist |

- Pretty much just a web developer |

- Boy howdy, I am bad at pandas |

---

## What happened

- I analyzed comments on an FCC proposal |

- Found some weird patterns, and published a blog post about it |

- The post ended up getting quite a bit of traction |

---

## A short description of the issue

- The head of the FCC wants to roll back Title II regulations |

- Most tech people do not support this |

- Most ISPs would very much like this proposal to suceed

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

- Started with Jupyter

- Moved to an Elasticsearch backend

- Analyzed the data with some Python scripts, storing the results in ES

- Used a Kibana frontend for easy data viewing

---

## First results

- There was an obvious "John Oliver" bump

- There were a lot of duplicate text entries

- The "John Oliver" comments were pretty easy to tag, but weren't identical

---

## Tagging

I started to "tag" comments, saving info like:

- Ingestion source (API, Web, CSV)
- Appoximately duplicate text
- Was there a full address?

---

# The Form Letters

+++

## "Unprecedented"

> The unprecedented regulatory power the Obama Administration imposed on the internet is smothering innovation, damaging the American economy and obstructing job creation. I urge the Federal Communications Commission to end the bureaucratic regulatory overreach of the internet known as Title II and restore the bipartisan light-touch regulatory consensus that enabled the internet to flourish for more than 20 years. The plan currently under consideration at the FCC to repeal Obama's Title II power grab is a positive step forward and will help to promote a truly free and open internet for everyone.

+++

## "Free our Internet"

> In 2015, President Obama's FCC passed rules treating the Internet as a government regulated public utility for the first time in history. Those pushing hardest for the new rules were Silicon Valley monopolies like Google and leftist globalists like George Soros. Google in fact visited the White House more than 427 times during the Obama years. Leftist foundations like Soros' Open Society and the Ford Foundation spent almost $200 million pushing for the rule change. Now we know why. In less than two years big tech and their liberal allies have taken total control of our information and communications platforms. They have used their power to flatten competitors, ban speech, censor content, routinely violate our privacy, and silence dissenting voices. While Obama's goal clearly benefited radical progressives, leftist political candidates, and his Silicon Valley corporate cronies it destroyed the free and open Internet by establishing them as our information gatekeepers. I strongly encourage the FCC to oppose efforts by the TechLeft and liberal globalists to take over our Internet. Please roll back President Obama's disastrous rules immediately. The future of a free and open Internet is at stake.

+++

## "Forced Regulations"

> Obama's Federal Communications Commission (FCC) forced regulations on the internet that put the government, and unaccountable bureaucrats, in control. These rules have cost taxpayers, slowed down broadband infrastructure investment, and hindered competition and choice for Americans. The time to remove the regulatory stranglehold on the internet is NOW. I urge the taxpayer-funded FCC to undo the terrible regulatory burdens that ex-FCC Chairman Tom Wheeler imposed on the internet. After 20 years, and trillions of dollars in infrastructure investment, there is no reason for the government to come in and ruin what has been a thriving tool that has changed the way we all live. Chairman Pai's proposal to repeal Title II regulations will ensure the continued growth of a dynamic, open internet for all American consumers and taxpayers.

+++

## "Diminished investment"

> Obama’s Title II order has diminished broadband investment, stifled innovation, and left American consumers potentially on the hook for a new broadband tax.
>
> These regulations ended a decades-long bipartisan consensus that the Internet should be regulated through a light touch framework that worked better than anyone could have imagined and made the Internet what it is.

+++

# "Demand Progress"

> A free and open internet is critical for Americans to connect with their friends and family, exercise their freedom of speech, and create innovative new businesses. In 2015, the FCC established strong net neutrality rules to protect the free and open internet Americans depend on. Please reject any plan from Trump or his FCC Chair to roll back net neutrality rules and open the door to a corporate controlled internet.

+++

# "Battle for the Net"

> The FCC Open Internet Rules (net neutrality rules) are extremely important to me. I urge you to protect them.
>
> I don't want ISPs to have the power to block websites, slow them down, make some more accessible than others, or split the Internet into "fast lanes" for companies that pay and "slow lanes" for the rest.
>
> Now is not the time to let giant ISPs censor what we see and do online.
>
> Censorship by ISPs is a serious problem. Comcast has throttled Netflix, AT&T blocked FaceTime, Time Warner Cable throttled the popular game League of Legends, and Verizon admitted it will introduce fast lanes for sites that pay—and slow lanes for everyone else—if the FCC lifts the rules. This hurts consumers and businesses large and small.
>
> Courts have made clear that if the FCC ends Title II classification, the FCC must let ISPs offer fast lanes to websites for a fee, and Chairman Pai has made clear that he intends to do just this.
>
> But if you let ISPs make some websites fast and others artificially slow—for a fee—you will kill the open marketplace that has enabled millions of small businesses and created the 5 most valuable companies in America—just to further enrich a few much less valuable cable giants famous for sky-high prices and abysmal customer service.
>
> I'm sending this to the FCC's open proceeding, but I worry that Chairman Pai, a former Verizon lawyer, has made his plans and will ignore me and millions of other Americans.
>
> So I'm also sending this to my members of Congress. Please publicly support Title II rules and denounce Chairman Pai's plans. Do whatever you can to dissuade him.
