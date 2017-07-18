1. *Think of a program you have used that is unacceptably slow. Identify the
specific operations that make the program slow. Identify other basic operations
that the program performs quickly enough.*

__A:__ I think of a CLI threaded newsreader I built in Python. It's slow in
organizing all the articles in a newsgroup into threads as it first downloads
all of their subjects and *then* organizes them. It can also get slow in
displaying specific articles as it has to download them first, and the speed of
that depends on the speed of the Internet connection. Operations which are
performed quick enough include formatting an article once it's downloaded and
writing a message to be sent to a local file before it's sent.
