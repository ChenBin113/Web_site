## 表单
表单用于搜集不同类型的用户输入，表单由不同类型的标签组成，实现一个特定功能的表单区域（比如：注册），

首先应该用<form>标签来定义表单区域整体，在此标签中再使用不同的表单控件来实现不同类型的信息输入，

具体实现及注释可参照以下伪代码：


    form定义一个表单区域,action属性定义表单数据提交的地址，method属性定义提交的方式。
    如果表单中含有文件上传 
    method提交方式必须为post 
    form中必须有enctype属性
    enctype="multipart/form-data"

> 表单中enctype="multipart/form-data"的意思，是设置表单的MIME编码。默认情况，这个编码格式是application/x-www-form-urlencoded，不能用于文件上传；
> 只有使用了multipart/form-data，才能完整的传递文件数据，进行下面的操作.enctype="multipart/form-data"是上传二进制数据; form里面的input的值以2进制的方式传过去


	<form action="#" method="POST">
	
	    <!-- label标签定义表单控件的文字标注，input类型为text定义了一个单行文本输入框 -->
	    <p>
	        <label>姓名：</label>
	        <input type="text" name="username" />
	    </p>
	
	    <!-- input类型为password定义了一个密码输入框 -->
	    <p>
	        <label>密码：</label>
	        <input type="password" name="password" />
	    </p>
	
	    <!-- input类型为radio定义了单选框 -->
	    <p>
	        <label>性别：</label>
	        <label><input type="radio" name="gender" value="0" /> 男</label>
	        <label><input type="radio" name="gender" value="1" /> 女</label>
	    </p>
	
	    <!-- input类型为checkbox定义了多选框 -->
	    <p>
	        <label>爱好：</label>
	        <label><input type="checkbox" name="like" value="eat" /> 吃饭</label>
	        <label><input type="checkbox" name="like" value="sleep" /> 睡觉</label>
	        <label><input type="checkbox" name="like" value="hit" /> 打豆豆</label>
	    </p>
	
	    <!-- input类型为file定义上传照片或文件等资源 -->
	    <p>
	        <label>照片：</label>
	        <input type="file" name="person_pic">
	    </p>
	
	    <!-- textarea定义多行文本输入 -->
	    <p>
	        <label>个人描述：</label>
	        <textarea name="about"></textarea>
	    </p>
	
	    <!-- select定义下拉列表选择 -->
	    <p>
	    <label>位置：</label>
	        <select name="site">
	            <option value="0">北京</option>
	            <option value="1">上海</option>
	            <option value="2">广州</option>
	            <option value="3">深圳</option>
	        </select>
	    </p>
	
	    <!-- input类型为submit定义提交按钮
	        还可以用图片控件代替submit按钮提交，一般会导致提交两次，不建议使用。如：
	        <input type="image" src="xxx.gif">
	    -->
	    <p>
	        <input type="submit" name="" value="注册">
	
	        <!-- input类型为reset定义重置按钮 -->
	        <input type="reset" name="" value="重置">
	    </p>
	
	</form>

<form action="#" method="POST">

    <!-- label标签定义表单控件的文字标注，input类型为text定义了一个单行文本输入框 -->
    <p>
        <label>姓名：</label>
        <input type="text" name="username" />
    </p>

    <!-- input类型为password定义了一个密码输入框 -->
    <p>
        <label>密码：</label>
        <input type="password" name="password" />
    </p>

    <!-- input类型为radio定义了单选框 -->
    <p>
        <label>性别：</label>
        <label><input type="radio" name="gender" value="0" /> 男</label>
        <label><input type="radio" name="gender" value="1" /> 女</label>
    </p>

    <!-- input类型为checkbox定义了多选框 -->
    <p>
        <label>爱好：</label>
        <label><input type="checkbox" name="like" value="eat" /> 吃饭</label>
        <label><input type="checkbox" name="like" value="sleep" /> 睡觉</label>
        <label><input type="checkbox" name="like" value="hit" /> 打豆豆</label>
	 </p>

    <!-- input类型为file定义上传照片或文件等资源 -->
    <p>
        <label>照片：</label>
        <input type="file" name="person_pic">
    </p>

    <!-- textarea定义多行文本输入 -->
    <p>
        <label>个人描述：</label>
        <textarea name="about"></textarea>
    </p>

    <!-- select定义下拉列表选择 -->
    <p>
    <label>位置：</label>
        <select name="site">
            <option value="0">北京</option>
            <option value="1">上海</option>
            <option value="2">广州</option>
            <option value="3">深圳</option>
        </select>
    </p>

    <!-- input类型为submit定义提交按钮
        还可以用图片控件代替submit按钮提交，一般会导致提交两次，不建议使用。如：
        <input type="image" src="xxx.gif">
    -->
    <p>
        <input type="submit" name="" value="注册">

        <!-- input类型为reset定义重置按钮 -->
        <input type="reset" name="" value="重置">
    </p>

</form>

<hr>

input表单项中的属性，可以提供

*type属性:表示表单项的类型:值如下:

    text:单行文本框

    password:密码输入框

    checkbox:多选框 注意要提供value值

    radio:单选框 注意要提供value值

    file:文件上传选择框

    button:普通按钮

    submit:提交按钮

    image:图片提交按钮

    reset:重置按钮, 还原到开始\(第一次打开时\)的效果

    hidden:主表单隐藏域,要是和表单一块提交的信息,但是不需要用户修改

*name属性:表单项名,用于存储内容值的

*value属性:输入的值\(默认指定值\)

size属性:输入框的宽度值

maxlength属性:输入框的输入内容的最大长度

readonly属性:对输入框只读属性

*disabled属性:禁用属性

*checked属性:对选择框指定默认选项

src和alt是为图片按钮设置的

> 注意：reset重置按钮是将表单数据恢复到第一次打开时的状态，并不是清空
> 
> image图片按钮，默认具有提交表单功能。

placeholder 属性规定可描述输入字段预期值的简短的提示信息（比如：一个样本值或者预期格式的短描述）。
> 
> 该提示会在用户输入值之前显示在输入字段中。
> 注意：placeholder 属性适用于下面的 input 类型：text、search、url、tel、email 和 password。
