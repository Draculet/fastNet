# 使用须知

* HttpHeaderParser类是一个保存状态的类,配合Buffer类使用来解析HTTP协议头部

* 由于该类保存HTTP协议头解析过程中的中间状态,即Buffer中可读的字节数小于一个完整的http请求时会等待连接下次可读,中间状态保存于类中,因此使用该类时需将其作为一个成员类来使用,切不可每次可读就重新构造一个新的该类,这种情况会造成解析中间状态丢失,解析失败.

* RequestHeader::toResp可用于将数据封装为HTTP Response后发送回对方

* webServer类是一个简单的example