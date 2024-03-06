# minpub

A Babashka script to generate a "minimum" EPUB eBook.

## Why

I had the need to generate an EPUB eBook from a large, structured
Markdown file. I didn't want to use a larger tool like Pandoc or
Calibre for this.  It was a little tricky to generate a minimal EPUB
that would open in both Calibre and Apple Books, so I wrote this
and am posting it here in case it's helpful to someone else.

The script `minpub.clj` generates an eBook based on a hard-coded,
short list of example chapters.  It's meant to serve as an example
rather than to be a general-purpose tool.

## Goals

- Fast (< 1 sec)
- Table of Contents with working cross-links
- Cover image
- Multiple chapters
- Openable in both Calibre and Apple Books

## Requirements

- [Babashka](https://github.com/babashka/babashka)
- `zip` command line tool

That's it!

## Example

```
>  time ./minpub.clj
{:exit 0, :out updating: META-INF/ (stored 0%)
updating: META-INF/container.xml (deflated 32%)
updating: epub/ (stored 0%)
updating: epub/images/ (stored 0%)
updating: epub/images/cover.png (deflated 0%)
updating: epub/toc.xhtml (deflated 51%)
updating: epub/content.opf (deflated 61%)
updating: epub/text/ (stored 0%)
updating: epub/text/chapter1.xhtml (deflated 34%)
updating: epub/text/introduction.xhtml (deflated 34%)
updating: epub/text/bonuschapter.xhtml (deflated 35%)
updating: epub/text/chapter2.xhtml (deflated 34%)
updating: epub/toc.ncx (deflated 61%)
updating: mimetype (stored 0%)
, :err }
EPUB 'book.epub' generated successfully.

real	0m0.154s
user	0m0.030s
sys	0m0.040s
>
```

## License

MIT

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
