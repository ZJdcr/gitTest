package main

import (
	"code.byted.org/gopkg/logs"
	item "code.byted.org/ide/demo-feature-test-kitex/kitex_gen/kitex/example/item/itemservice"
)

func main() {
	svr := item.NewServer(new(ItemServiceImpl))

	err := svr.Run()

	if err != nil {
		logs.Error("%s", err.Error())
	}
	logs.Stop()
}
