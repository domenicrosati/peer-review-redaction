# Peer Review Redaction

Peer Reviews documents that review a research article before it's publication that are an outcome of a peer review process.
Peer Review processes all tend to be different and one of the main ways they differ is anonymity.
While not all peer review documents or peer reviewers are required to be anonymous.
A process for anonymizing them by redaction of personally identifying information could be useful by academic publishers or conferences who want to make this content available.
Primarily this would be to protect the anonymity of the reviewer rather than the reviewee but both approaches are possible to investigate.
The purpose of this project is to illustrate methods for redacting identifying information from peer review documents.

Using the a peer review dataset we'd like to ask the follwing questions:
- How prevelant is identifying information in Peer Review Documents?
- How can we automatically remove identifying information.

## Methods Explored

Dataset used: [https://github.com/allenai/PeerRead](https://github.com/allenai/PeerRead)

### How prevelant is identifying information in Peer Review Documents?

The primary method for initial exploration is as follows:
1. For each document we extract the text and the metadata.
2. We extract PERSON mentions from the review text

Then we can write that to a filter for analysis.

### How can we automatically remove identifying information?

TBD

## Analysis

Spot checking I have only found one indication of personally identifying information:
```
{
"people": [
    "J. Mu",
    "P. Viswanath"
],
"review": "We (J. Mu and P. Viswanath) thoroughly enjoyed the authors' previous work on linear algebraic structure of word senses (cf. "
},
```

## Going Forward

The primary issue for doing this automatically with a canned NER is that we don't want to redact valuable citation, author, work recommendations.
So going forward redacting PII would require either:
- A parsing approach where we can build rules such as whether a personal name is used to refer to a personal pronoun or not, or use some kind of Co-reference resolution with rueles approach.
- Annotatation and training to find these as distinct entities.
