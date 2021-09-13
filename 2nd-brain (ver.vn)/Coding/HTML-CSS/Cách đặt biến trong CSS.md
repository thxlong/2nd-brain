- Ta đặt biến trong `:root`, 
- Một biến bắt đầu bằng dấu `--` - ví dụ: `--text-color: #fff`
-  Để gọi biến đó ra ta dùng `var()` - ví dụ: `var(--text-color: #fff)`
*Example*
````css
:root{
	--text-color: #fff
}

.title{
	color: var(--text-color: #fff)
}

.text{
	color: var(--text-color: #fff)
}
````