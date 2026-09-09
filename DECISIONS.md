# Decisions

A decision log: what you chose and why, in your own words.
P1 uses a file with this name and five questions; this one has one.
Answer it in two or three sentences after the live page is verified, then commit and push it.

## How you know it works

What check did you run on the live page, and what would have made that check fail?
A check that could not have failed is not a check.

I verified the deploy in two ways: the agent polled the build until its status read "built," then fetched the live URL and confirmed it returned HTTP 200 with my sentence present in the page text; separately, I loaded the URL in a browser and took a screenshot with the address bar visible to confirm the page rendered correctly at the real domain. This was a real check because it could have failed several ways - the build could have stayed "queued" or come back "errored," the fetch could have returned HTTP 200 but with the old placeholder text still on the page (meaning the latest commit had not actually deployed), or the page could have loaded unstyled (black text on white) if style.css had not linked correctly - and none of those happened.
