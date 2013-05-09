---
layout: post
title: ProjectEuler 22
---
22  
先对数据进行预处理和排序工作，然后再用C语言实现剩余的步骤。
<pre class="prettyprint lang-bash">
sed -e 's/\"//g' /tmp/names.txt | tr , "\n" |sort|tcc -run euler22.c
</pre>
<pre class="prettyprint">
//euler22.c
#include <stdio.h>

int main()
{
	char name[10];
	int i,j,score=0;
	for (i=1;scanf("%s",name)!=EOF;++i){
		int worth=0;
		for (j=0;name[j];++j){
			worth+=name[j]&0xbf;
		}
		score+=worth*i;
	}
	printf("%d\n",score);
	return 0;
}
</pre>

