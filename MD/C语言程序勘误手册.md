# C����BUG�޸ļ�¼

<center>2023��7��19��</center>

---

* ͨѶ�ײ��ļ�[CAN_Com_process.h]

```
#define BTIM_TABLE    {\//  PripheralClock=36MHz������
   {CAN_RSJW_1tq,CAN_TBS1_10tq,CAN_TBS2_1tq,3},\
   {CAN_RSJW_1tq,CAN_TBS1_8tq,CAN_TBS2_1tq,4},\
   {CAN_RSJW_2tq,CAN_TBS1_13tq,CAN_TBS2_1tq,3},\
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,3},\
   {CAN_RSJW_1tq,CAN_TBS1_13tq,CAN_TBS2_1tq,4},\
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,4},\
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,5},\
   {CAN_RSJW_1tq,CAN_TBS1_15tq,CAN_TBS2_1tq,7},\
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,8},\
   {CAN_RSJW_1tq,CAN_TBS1_14tq,CAN_TBS2_1tq,10},\
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,10},\
   {CAN_RSJW_1tq,CAN_TBS1_13tq,CAN_TBS2_1tq,15},\
   {CAN_RSJW_1tq,CAN_TBS1_14tq,CAN_TBS2_1tq,15},\// 150K
   {CAN_RSJW_1tq,CAN_TBS1_8tq,CAN_TBS2_1tq,25},\// 144K
   {CAN_RSJW_1tq,CAN_TBS1_6tq,CAN_TBS2_1tq,36},\// 125K
   {CAN_RSJW_1tq,CAN_TBS1_13tq,CAN_TBS2_1tq,20},\// 120K
   {CAN_RSJW_1tq,CAN_TBS1_6tq,CAN_TBS2_1tq,45},\// 100K
   {CAN_RSJW_1tq,CAN_TBS1_14tq,CAN_TBS2_1tq,25},\// 90K
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,25},\// 80K
   {CAN_RSJW_1tq,CAN_TBS1_14tq,CAN_TBS2_1tq,30},\// 75K
   {CAN_RSJW_1tq,CAN_TBS1_13tq,CAN_TBS2_1tq,40},\// 60K
   {CAN_RSJW_1tq,CAN_TBS1_14tq,CAN_TBS2_1tq,45},\// 50K
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,50},\// 40K
   {CAN_RSJW_1tq,CAN_TBS1_14tq,CAN_TBS2_1tq,75},\// 30K
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,100}}// 20K
```
�м���Щע��ɾ���ˣ���ɾ��ע�͵ĵط��ǲ�����ģ�����ע�͵ĵط�������
```����
Error[Pe007]: unrecognized token E:\OneDrive\E35&CAN_PROJX\CAN_Com_JXPR\projects\CAN_Com_JXPR\inc\CAN_Com_process.h 81 
```
����������򲿷����Ǵ�ǰһ���汾copy�����ģ�Ϊʲôԭ���ĳ��򲻱�������
```User_Can_Config.c
/* ������������BTIM�Ĵ������ñ�*/
const tCAN_BaudRate  CAN_BaudRateInitTab[]= {      // CLK=36MHz
   {CAN_RSJW_1tq,CAN_TBS1_10tq,CAN_TBS2_1tq,3},     // 1M
   {CAN_RSJW_1tq,CAN_TBS1_8tq,CAN_TBS2_1tq,4},     // 900K
   {CAN_RSJW_2tq,CAN_TBS1_13tq,CAN_TBS2_1tq,3},     // 800K
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,3},     // 666K
   {CAN_RSJW_1tq,CAN_TBS1_13tq,CAN_TBS2_1tq,4},     // 600K
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,4},     // 500K
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,5},     // 400K
   {CAN_RSJW_1tq,CAN_TBS1_15tq,CAN_TBS2_1tq,7},    // 300K
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,8},    // 250K
   {CAN_RSJW_1tq,CAN_TBS1_14tq,CAN_TBS2_1tq,10},	// 225K
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,10},    // 200K
   {CAN_RSJW_1tq,CAN_TBS1_13tq,CAN_TBS2_1tq,15},	// 160K
   {CAN_RSJW_1tq,CAN_TBS1_14tq,CAN_TBS2_1tq,15},    // 150K
   {CAN_RSJW_1tq,CAN_TBS1_8tq,CAN_TBS2_1tq,25},		// 144K
   {CAN_RSJW_1tq,CAN_TBS1_6tq,CAN_TBS2_1tq,36},   // 125K
   {CAN_RSJW_1tq,CAN_TBS1_13tq,CAN_TBS2_1tq,20},	// 120K
   {CAN_RSJW_1tq,CAN_TBS1_6tq,CAN_TBS2_1tq,45},    // 100K
   {CAN_RSJW_1tq,CAN_TBS1_14tq,CAN_TBS2_1tq,25},   // 90K
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,25},   // 80K
   {CAN_RSJW_1tq,CAN_TBS1_14tq,CAN_TBS2_1tq,30},	// 75K
   {CAN_RSJW_1tq,CAN_TBS1_13tq,CAN_TBS2_1tq,40},    // 60K
   {CAN_RSJW_1tq,CAN_TBS1_14tq,CAN_TBS2_1tq,45},    // 50K
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,50},    // 40K
   {CAN_RSJW_1tq,CAN_TBS1_14tq,CAN_TBS2_1tq,75},   // 30K
   {CAN_RSJW_1tq,CAN_TBS1_16tq,CAN_TBS2_1tq,100},   // 20K
};
```
<center>2023��7��27��</center>

---

��������⡿IARͻȻ�ر𿨡�������������µ��ļ�·���������ġ����桱
��������⡿û�а취����Ѱ�����Ѱ��������ת���������clean�����±���

<center>2023��8��23��</center>

---

* ������κ꣬�������ַ����Ӻ���������⣡����

```�ַ����Ӻ궨��
//Tools.h
#define _toString(str)			#str
#define toString(str)				_toString(str)
#define _conStr(a, b)				(a##b)
#define conStr(a, b)				_conStr(a, b)
#define _conStr3(a, b, c)		(a##b##c)
#define conStr3(a, b, c)		_conStr3(a, b, c)
//CanPrtcl1_Instantiator.c
/* ��Щֵ������Ϊ��ֵ��ֵ�ģ�������������顰{A,B,C,...}��*/
#define Prtcl1_INFO               conStr3(Prtcl_,_Prtcl1,_Info)
#define Prtcl1_TXMSG_L            conStr3(Prtcl_,_Prtcl1,_TXMSG_L)
#define Prtcl1_RXMSG_L            conStr3(Prtcl_,_Prtcl1,_RXMSG_L)
#define Prtcl1_TXMSG1_SGN_L       conStr3(Prtcl_,_Prtcl1,_TXMSG1_SGN_L)
#define Prtcl1_RXMSG1_SGN_L       conStr3(Prtcl_,_Prtcl1,_RXMSG1_SGN_L)
#define Prtcl1_TXMSG1_SPU_L       conStr3(Prtcl_,_Prtcl1,_TXMSG1_SPU_L)
#define Prtcl1_RXMSG1_SPU_L       conStr3(Prtcl_,_Prtcl1,_RXMSG1_SPU_L)

/* �źű��ۻ������б�*/
const float Prtcl1_TxMsg1_SgnPeru_l[Prtcl1_TxMsg1_SgnNum] = Prtcl1_TXMSG1_SPU_L;
const float Prtcl1_RxMsg1_SgnPeru_l[Prtcl1_RxMsg1_SgnNum] = Prtcl1_RXMSG1_SPU_L;
/* �źŲ����б�*/
const Signal_t Prtcl1_TxMsg1_Sgns_l[Prtcl1_TxMsg1_SgnNum] = Prtcl1_TXMSG1_SGN_L;/* [Error:"Prtcl1_TXMSG1_SGN_L"expected a constant value.] */
const Signal_t Prtcl1_RxMsg1_Sgns_l[Prtcl1_RxMsg1_SgnNum] = Prtcl1_RXMSG1_SGN_L;/* Error */
/* ��Ϣ�����б�*/
const CanMsg_t Prtcl1_TxMsg_l[Prtcl1_TxMsgNum] = Prtcl1_TXMSG_L;/* Error */
const CanMsg_t Prtcl1_RxMsg_l[Prtcl1_RxMsgNum] = Prtcl1_RXMSG_L;/* Error */
/* Э�����Ϣ*/
const CanNodePrtcl_t Prtcl1 = Prtcl1_INFO;/* Error */
```
> ��������Ϊ����չ����({A,B,C,...})��Ϊ��ֵ����֪����������������Ϊ��ʲô�����϶��ǷǷ��ġ�
> ���������Option->C/C++ Compiler->Preprocesser output to fileѡ��򿪣���Debug/List/xxx.i����Ԥ�������ļ����鿴Ԥ�������⡣


* ����IAR�������е��������⣬������������������ָ�롣
> ��������ָ������ַ�����
> 1. �����������ͣ����������Ͷ�������ָ�롣
> 2. ��������ָ�����ͣ�������ָ��ֱ�Ӷ��塣
> 3. ֱ�Ӷ���

```
//��һ��
int a[10] = {0};
typdef int A[10];       //[10]������
                        //����ָ���ָ�������:
                        //����ָ��Ĳ�����sizeof(int)*10��ָ��Ĳ�����sizeof(int)
A *p = NULL;            //p����ָ�����͵ı���!!!!!!

//�ڶ���
int a[10] = {0};
typedef int(*P)[10];
P q;                        //����ָ�����

//������
int a[10] = {0};
int(*q)[10];                //q����ָ�����

```

<center>2023��8��28��</center>

---

* ע���������⣬�����Ǻ�����/�ṹ����������������ʹ�����ַ��Ϊ��ֵ��ʼ����������ʱ��һ��Ҫ��ȡ��ַ���㣬��Ϊ��ʼ��Ҫ����ֵ�����ǳ��������ոն����������ָ��������Ǻ���ָ�룬���ʶ��Ǳ�����������Ϊ��ֵ��

```
typedef struct{
  uint32_t            ID;
  uint8_t             MsgType;          /* CAN_Message_Type*/
  uint8_t             SignalNum;
  uint8_t             Length;
  uint8_t             SendType;         /* CAN_MessageSend_Type*/
  uint32_t            Cycle_ms;
  Signal_t const      *pSgnList;
  Callback_fp const   *callback;//���Ͷ���ʱҪ�ö���ָ��
  SignalsInf_t const  *SignalsInf;
}CanMsg_t;

//���庯��ָ��
extern Callback_fp Prtcl1_TxMsg1_callback;
extern Callback_fp Prtcl1_RxMsg1_callback;

//��ֵʱȡ��ַ
const CanMsg_t Prtcl1_TxMsg_l[1] = {{0x51A,((uint8_t)0x00),7,8, ((uint8_t)0x00),100,\
Prtcl1_TxMsg1_Sgns_l, &Prtcl1_TxMsg1_callback,&Prtcl1_TxMsg1_SgnInf_l}};
```

* �ܶ�Ԥ������������ͨ����.i�ļ����������.i�ļ��õ����������Կ�����չ����Ľ����


<center>2023��9��12��</center>

---

* GPIO�ĳ�ʼ�������У�GPIO_Speed��Աһ��Ҫ��ʼ������
��Ϊ�ں�����һ��ֻ����ʱ������Ϊ�����ʼ�����������粻��ʼ���Ļ�������ֵ�ǲ�ȷ���ģ���GPIO_Speed��Ա����ö���ͱ������������ʼ�����ᵼ�������ʼ�������Ĳ�����鲻ͨ�������³�ʼ��ʧ�ܣ���