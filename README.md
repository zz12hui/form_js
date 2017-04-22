# 一个简单的表单验证
//表单验证开始
 $('#appsubmit').live('click',
	function() {
		  var name = $('#name').val();
		  var tel = $('#lxdh').val();
		  var weixin=$('#weixin').val();
		  var rename=/[\u4e00-\u9fa5]/g;   //匹配中文字符
		  var retel=/^1(3|4|5|7|8)\d{9}$/;    //匹配国内手机号
		  //姓名验证，中文字符不超过四个字符，避免复姓无法提交
		if (name == '') {
			alert('亲，您的姓名忘记填写了！');
			$('#name').focus();
			return false;
			}
		else if(!rename.test(name)){
		 	alert('请输入正确的姓名！');
			$('#name').focus();
			return false;
			}
		else if(name.length<2){
			alert('亲~您的姓名还没写全！');
			$('#name').focus();
			return false;
			}
		else if(name.length>4){
			alert('亲~您的名字太长啦！');
			$('#name').focus();
			return false;
			}
		else if (tel+weixin!=""){//电话验证，目前只验证手机号，以后有更新
				if(weixin=="")
				{
					 $("#weixin").attr("value",'未填写微信！');
				}else if(tel=="")
				{
					$("#lxdh").attr("value",'未填写手机！');
				}
					alert('感谢您的提交！');
				}
				else
				{
					alert('亲，您的QQ/微信/手机号忘记填写了！');
					$('#weixin').focus();
					return false;
				}
});

