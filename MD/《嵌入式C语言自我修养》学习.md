# Ƕ��ʽC������������

<center>2023��7��18��</center>
---

# ��6��-GNU C��������չ�﷨����


#define offsetof(type,member)   ((size_t)&(((type*)0)->member))        //ȡmember��Ա��type�����е�ƫ�Ƶ�ַ
#define container_of(ptr,type,member)   ({              \
    const (typeof((type*)0->member)) *_mptr = (ptr);    \              //����ָ���ͱ���ȡֵ����ֹ�������һ������֮��ı��ʽ
    (type*)((char*)_mptr - offset(type,member));        \              //ǿ��ת��Ϊchar����
})
