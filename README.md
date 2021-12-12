# Lesson_bash_netology
1. #!/bin/bash
a=1
b=3
c=a+b
d=$a+$b
e=$(($a+$b))
echo $c
echo $d
echo $e

ответ:
a+b (Неявное определение строки)
1+3 (Неявное определение целочисленного)
4    (явное определение целочисленного)

2. необходимо в скрипт добавить цикл.
я попробовал это сделать, но что то не получается запустить.
вот мой измененный скрипт:
#!/bin/bash
i=0
while ((1==1))
do
echo $i
let "I+=1"
sleep 3
if [ $1 == 5 ]
then
break
elif ((1==1))
curl https://localhost:4757
if (($? != 0))
then
date >> curl.log
fi

можете пожалуйста подсказать в правильном направлении движусь ли?
Спасибо.

3.
#!/bin/bash
cat check_hosts
hosts=(192.168.0.1 173.194.222.113 87.250.250.24)
timeout=5
for i in {1..5}
do
date >> hosts.log
    for h in ${hosts[@]}
    do
	curl -Is --connect-timeout $timeout $h:80 >/dev/null
        echo "check" $h status=$? >> hosts.log
    done
done

4.
#!/bin/bash
cat check2_hosts
hosts=(192.168.0.1 173.194.222.113 87.250.250.24)
timeout=5
res=0
while (($res == 0))
do
    for h in ${hosts[@]}
    do
	curl -Is --connect-timeout $timeout $h:80 >/dev/null
	res=$?
	if (($res != 0))
	then
	    echo "ERROR on" $h status=$res >> hosts2.log
	fi
    done
done