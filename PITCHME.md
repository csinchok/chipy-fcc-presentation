# Tracking Bots with Python 

Chris Sinchok

---

### Who am I?

- Not a data scientist |
- Pretty much just a web developer |
- Boy howdy, am I bad at pandas |

---

### What happened

- I analyzed comments on an FCC proposal |
- Found some weird patterns, and published a blog post about it |
- The post ended up getting quite a bit of traction |

### A short description of the issue

- The head of the FCC wants to roll back Title II regulations |
- Most tech people do not support this |
- Most ISPs support it very much |

### Public Comments?

- Any time the FCC has a proposal, they solicit public comments |
- Comments are *not* an actual vote |
- Public sentiment has swayed things before |

### My initial goals

- Get an idea of the overall public sentiment
- Look at how much John Oliver changed the numbers
- Build a website to provide an analysis of the data

### The FCC has a Comment API!

- Returns JSON
- With an API key, allows posting of comments
- Drives the ECFS frontend

### The Data

```JSON
{
    "id_submission": "105100904707408",
    "addressentity": {
        "city": "Chicago",
        "address_line_1": "1322 W Barry Ave",
        "address_line_2": "Apt 1",
        "state": "IL",
        "zip_code": "60657"
    },
    "contact_email": "chris@sinchok.com",
    "filers": [
        {
            "name": "Chris Sinchok"
        }
    ],
    "date_submission": "2017-05-10T00:19:56.405Z",
    "date_received": "2017-05-10T00:19:56.405Z",
    "date_disseminated": "2017-05-10T15:12:58.923Z",
    "text_data": "I strongly support keeping ISP's regulated under Title II, and am *very* against this proposal, which I believe threatens the neutrality of the internet.",
}
```

@[2](Every comment has a unique ID)
@[3-9](Address isn't required, but it's often present)
@[10](Email isn't visible on the web frontend, but it's available in the API)
@[16-17](These dates are effectively the same--they're the time I made the comment)
@[18](This is the date the comment was approved and posted to the website)
@[19](The text data itself)