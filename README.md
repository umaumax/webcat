# webcat

## requires
* [umaumax/gonetcat]( https://github.com/umaumax/gonetcat )
* [umaumax/gocat]( https://github.com/umaumax/gocat )
* [umaumax/gechota]( https://github.com/umaumax/gechota )
* [yudai/gotty: Share your terminal as a web application]( https://github.com/yudai/gotty )

```
go get -u github.com/umaumax/gonetcat
go get -u github.com/umaumax/gocat
go get -u github.com/umaumax/gechota

go get -u github.com/yudai/gotty
```

## how to use
```
export WEBCAT_PORT=3939
```

```
function _webcat() {
  gonetcat localhost $WEBCAT_PORT
}
function webcat() {
  # screen clear and clear font
  gocat -prefix='\x1b[2J\x1b[1;1H\033[0m' -suffix='# END\n' | _webcat "$@"
}
function webcatd() {
  gotty $(which gechota) -p=$WEBCAT_PORT &
}
```
