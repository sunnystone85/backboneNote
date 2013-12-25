Model的对象里面有previousAttributes的Object是用来记录原来的属性的比如有name属
性，当name被修改之后previousAttributes中会记录name原来的值，新的值在attributes中changed对象会记录那写属性做了什么样的变更。


需要注意的一点是在model.save()后，服务端接收post过去的信息时，php是不能直接用$_POST获取json的，因为header application/json;
所以我们需要 <br/>
<div>
header('Content-Type: application/json; charset=utf-8');  <br/>
$json = file_get_contents("php://input"); <br/>
</div>
