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

---

### A short description of the issue

- The head of the FCC wants to roll back Title II regulations |
- Most tech people do not support this |
- Most ISPs support it very much |

---

### Public Comments?

- Any time the FCC has a proposal, they solicit public comments |
- Comments are not an actual vote |
- Public sentiment has swayed things before |

---

### My initial goals

- Get an idea of the overall public sentiment |
- Look at how much John Oliver changed the numbers |
- Build a website to provide an analysis of the data |

---

### The FCC has a Comment API!

- Returns JSON |
- With an API key, allows posting of comments |
- Drives the ECFS frontend |

---?code=my-comment.json&lang=json

### A brief tour of the Data

@[2](Every comment has a unique ID)
@[19-25](Address isn't required, but it's often present)
@[26](Email isn't visible on the web frontend, but it's available in the API)
@[35-36](These dates are effectively the same--they're the time I made the comment)
@[37](This is the date the comment was approved and posted to the website)
@[99](The text data itself)