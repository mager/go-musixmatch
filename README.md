# Go-Musixmatch!

This is a Go wrapper for working with the [Musixmatch](https://www.musixmatch.com/) API.

Documentation can be found at: [Go-Musixmatch Documentation](https://pkg.go.dev/github.com/milindmadhukar/go-musixmatch)

It aims to support every task listed in the Web API Endpoint Reference, located [here](https://developer.musixmatch.com/documentation).

_All of the API endpoints are covered except the premium ones._

## 💻 Installation

To install the library simply open a terminal and type:

```
go get github.com/milindmadhukar/go-musixmatch
```

## ️️🛠️ Tools Used

This project was written purely in `Golang` for `Golang`.</br>
The module helps with the usage of the [Musixmatch](https://developer.musixmatch.com/documentation) API.

## ⛏️ Acquiring Musixmatch API Key.

1. Go to the [Musixmatch Developer Page](https://developer.musixmatch.com/plans) and select a plan.
1. Fill in the necessary details to create an account and verify it from your email.
1. Go to your [Account Dashboard](https://developer.musixmatch.com/admin/applications) and you should see an API Key.
1. Note the API Key down and don't reveal it to anyone.

## 🏁 Basic Setup:

For all the endpoints and parameters that can be used, check the [Musixmatch API docs](https://developer.musixmatch.com/documentation)

```go
package main

import (
	"context"
	"fmt"
	"log"
	"net/http"

	mxm "github.com/milindmadhukar/go-musixmatch"
	"github.com/mager/go-musixmatch/params"
)

func main() {

	client := mxm.New("<YOUR API KEY>", http.DefaultClient)

	artists, err := client.SearchArtist(context.Background(), params.QueryArtist("Martin Garrix"))
	if err != nil {
		log.Fatal(err)
	}

        fmt.Println(artists[0])

}
```

### Output

```go
{24407895 Martin Garrix [91 93]  NL [{MARTIJN GARRITSEN}] 67  {[]} 0 2017-02-03 07:02:12 +0000 UTC 1996 1996-05-15  0000-00-00}
```

## Missing Features / Known Bugs

_These features are not implemented as they are premium users only and give me a 401. If you have access to the endpoints and would like to contribute, please open a PR._

#### Unimplemented Endpoints

- <a href="https://developer.musixmatch.com/documentation/api-reference/track-lyrics-post" target="_blank">track.lyrics.post</a>
- <a href="https://developer.musixmatch.com/documentation/api-reference/track-lyrics-mood-get" target="_blank">track.lyrics.mood.get</a>
- <a href="https://developer.musixmatch.com/documentation/api-reference/track-richsync-get" target="_blank">track.richsync.get</a>
- <a href="https://developer.musixmatch.com/documentation/api-reference/track-lyrics-translation-get" target="_blank">track.lyrics.translation.get</a>
- <a href="https://developer.musixmatch.com/documentation/api-reference/track-subtitle-translation-get" target="_blank">track.subtitle.translation.get</a>
- <a href="https://developer.musixmatch.com/documentation/api-reference/tracking-url-get" target="_blank">tracking.url.get</a>
- <a href="https://developer.musixmatch.com/documentation/api-reference/catalogue-dump-get" target="_blank">catalogue.dump.get</a>
- <a href="https://developer.musixmatch.com/documentation/api-reference/work/work.post" target="_blank">work.post</a>
- <a href="https://developer.musixmatch.com/documentation/api-reference/work/work.post" target="_blank">work.validity.post</a>
- <a href="https://developer.musixmatch.com/documentation/api-reference/track-subtitle-get" target="_blank">track.subtitle.get</a>
- <a href="https://developer.musixmatch.com/documentation/api-reference/matcher-subtitle-get" target="_blank">matcher.subtitle.get</a>

## 🧿 Extras

_There is supposed to be something here idk_

Thats it, have fun ✚✖
