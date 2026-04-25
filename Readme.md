# 👁️ Open Shinigami Eyes - Dataset Explorer (Unofficial)

An **unofficial transparency tool** for inspecting the dataset behind the bloom filters used by Shinigami Eyes.
This project attempts to **enumerate and test real-world usernames/domains** against the published bloom filters to give a rough idea of what the extension “sees.”

***

## 🔍 What this does

We use a **brute-force enumeration approach** across popular platforms, including:

* Twitter / X
* Bluesky
* Mastodon
* Facebook
* Reddit
* Tumblr
* YouTube
* Wikipedia

Usernames, handles, and domains from these platforms are checked against:

* `bloomfilter_26021801_tfriendly.dat`
* `bloomfilter_26021801_transphobic.dat`

If a match is detected, it is included in the dataset.

***

## 🎯 Goal

Bloom filters are intentionally opaque and **cannot be reversed directly**.
This project exists to:

* Provide **transparency** into what *may* be inside the filters
* Help researchers and developers **analyze patterns**
* Offer a **practical approximation** of the dataset

***

## ⚠️ Limitations

This is important—don’t skip it.

### 1\. Not a complete dataset

This is **not a dump of the original data**.
It only includes entries that were successfully guessed and matched.

### 2\. False positives \(hash collisions\)

Bloom filters are probabilistic.

* Some matches **may not actually exist** in the original dataset
* Collisions are expected and unavoidable

### 3\. Coverage bias

Results depend heavily on:

* Which platforms were scanned
* Which usernames/domains were tested

This means the dataset is **incomplete and biased toward popular or guessable names**.

***

## 🚫 What this is NOT

* ❌ Not used to generate the original bloom filters
* ❌ Not an official dataset
* ❌ Not affiliated with the original project
* ❌ Not guaranteed to be accurate

This is strictly a **lookup tool against existing bloom filter files**.

***

## 🧠 How it works (high-level)

1. Collect candidate usernames/domains from supported platforms
2. Normalize them into the format expected by the filter
3. Hash and test against the bloom filters
4. Record matches

Because bloom filters only support **membership checks**, this process relies entirely on **guessing inputs and testing them**.

***

## 📂 Data Sources

All results are derived from:

* `bloomfilter_26021801_tfriendly.dat`
* `bloomfilter_26021801_transphobic.dat`

No additional private or hidden datasets are used.

***

## ⚖️ Ethical Notes

* This project is intended for **research, transparency, and analysis**
* Results should be treated as **probabilistic, not definitive**
* Do not use this dataset for harassment, targeting, or automated decision-making

***

## 🙋 FAQ

**Q: Can this reveal the full dataset?**
No. Bloom filters are one-way probabilistic structures.
**Q: Are the results accurate?**
Some are, some aren’t. False positives are expected.
**Q: Why brute force?**
Because there is no other practical way to inspect a bloom filter externally.
