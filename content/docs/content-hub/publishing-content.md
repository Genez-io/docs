# Publishing Content

Genezio writes and stores content. Publishing happens on your own site, and
how you publish affects whether the piece can be cited at all.

---

## Getting the content out

Copy the article into your CMS, or export it. The text is the straightforward
part; the two things teams forget are below.

---

## Take the schema markup with it

Every article carries its [schema.org markup](schema-markup.html). Paste it
into the page as a JSON-LD block, or into your CMS's structured-data field.

Without it an engine has to infer what the page is from the prose, and it is
often wrong. With it, the page is also eligible for rich results it otherwise
cannot get.

---

## Publish it where it can be read

A page that answer engines cannot retrieve cannot be cited, however good it is:

- **Not behind a login or a form.** Gated content is invisible to engines.
- **Not only in a PDF, an image or a video.** If the substance is not in text
  on the page, there is nothing to lift. A video needs a transcript.
- **On a crawlable URL.** A page excluded in `robots.txt` or marked `noindex`
  is excluded from the retrieval that feeds answers.

---

## Then measure it

Publishing is the start of the measurement, not the end of the work.

1. Note the date.
2. Keep running the topics the piece targets.
3. Watch whether the page starts appearing in
   [Most Cited Sources](../insights/most-cited-sources.html).

Citation usually lags publication by weeks, because engines have to find the
page and decide it is worth using. A piece that has not been cited after one
run has not failed.

If it is still absent after several, read what *is* being cited for that
question and compare honestly.
