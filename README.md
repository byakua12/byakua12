x///////x///////x///////x///////x//////
//
//  AVPX  AVP eXtender   Seek&Enjoy! X-)   (x) 1998-2003 Z0MBiE
//  AVPX is a FREEWARE .AVC file unpacker
//
//  to compile: bcc32 avpx.cpp
//
////////x///////x///////x///////x///////x///////x///////x///////x///////x//////
//
//AVPX 3.30        1-05-2003
//
//  - fixed bug with zero unpacked size of *.l16
//
//AVPX 3.29        6-02-2001
//
//  - keywords supported (256 max):
//    only OBJ/stamm entries containing one of keywords will be extracted.
//
//AVPX 3.28       17-01-2001
//
//  - now all options may have '-' postfix, which means reverse effect
//  - '/ren' option added, automatically rename obj-files
//  - added _objname1.bat & _objname2.bat instead of _objname.bat
//  - added COFF OBJ time dump -- _objtime.txt. (32-bit OBJs required)
//  - generated files date/time is now set to original values
//
//AVPX 3.27       24-08-2000
//
//  - dynamically linked library removed
//  - bugfix (compiler error: [ESP].based locals were used in the inline asm,
//            but PUSHA was ignored by BCC32. see src)
//
//AVPX 3.26       15-03-00
//
//  - supported AVCs without "names" (DAILY.AVC)
//  - AVPX is now compiled with BCC5, so CW3230.DLL required.
//  - AVPX.EXE is now packed with UPX
//
//AVPX 3.25       26-01-00
//
//  - stamm dump bugfixed
//
//AVPX 3.24        6-01-00
//
//  - ¨á¯à ¢«¥­ë £«îª¨ á ª®¬ ­¤­®© áâà®ª®©, etc.
//  - ¤®¡ ¢«¥­ ¯¥à¥¬¥âà /qq -- ¬®«ç âì á®¢á¥¬
//  - ¤®¡ ¢«¥­ ¯¥à¥¬¥âà /p
//
//AVPX 3.23        5-01-00
//
//  - ®¯æ¨ï /nh -- ­¥ á®§¤ ¢ âì å¥ ¤¥àë (¡¨­ à­ë¥ ¨ ¨å â¥ªáâ®¢ë¥ ®¯¨á ­¨ï .txt)
//  - ®¯æ¨ï /ns -- ­¥ á®§¤ ¢ âì èâ ¬¬ë
//                 (¡¨­ à­ë¥ ¨ ¨å â¥ªáâ®¢®¥ ®¯¨á ­¨¥ _stamm.txt)
//  - ¤®¡ ¢«¥­ AVPX.CFG, ¬®¦¥â «¥¦ âì ¢ â®© ¦¥ ¤¨à¥ çâ® ¨ AVPX.EXE,
//    ¯® ®¤­®¬ã á¢¨çã ­  áâà®ª¥
//
//AVPX 3.22        4-01-00
//
//  - ®â­ë­¥ ¬®¦­® ¯®¤ ¢ âì ­¥ ®¤­® ¨¬ï AVC-ä ©« ,   ¬ áªã ®­ëå
//  - ¤®¡ ¢«¥­  ®¯æ¨ï /names -- £¥­¥à¨âì  ä ©« _names (¨¬¥­  âà¥¯ ª®¢)
//  - ¤®¡ ¢«¥­  ®¯æ¨ï /q -- ¬®«ç âì (quiet)
//  - ¤®¡ ¢«¥­  ®¯æ¨ï /a -- ¨¬¥­  ¤®¡ ¢«ïâì ª á¯¨áªã _names  ¯¯¥­¤®¬
//  - ¤®¡ ¢«¥­ë æ¢¥â  ¢ ª®­á®«ì­ë© output
//
//AVPX 3.21       17-12-99
//
//  - ­¥¬­®£® ¯®¯à ¢«¥­ ¨áå®¤­¨ª; â¥¯¥àì ª®¬¯¨«¥à BCC 5.2 ¨ ä ©« ¢ëà®á ­  ~30k
//  - â¥¯¥àì áâ¨à îâáï lnkNNNN.dat-ä ©«ë ¯à¨ ¢ëå®¤¥;
//    ®¯æ¨ï /k ®â¬¥­ï¥â á¨¥ ¤¥©áâ¢®;
//  - ¢ ¨¬¥­ å á®àæ®¢ ®¡¦¥© á¨¬¢®«ë \ § ¬¥­ïîâáï ­  @
//  - á®§¤ ¥âáï á¯¨á®ª ¨¬¥­ ¢¨àãá®¢ (ä ©« _names)
//
//AVPX 3.20        1-07-99
//
//  - ¯®ä¨ªá¥­  á¨âã æ¨ï á ®âáãâáâ¢¨¥¬ 64-¡ ©â®¢®© ¯®¤¯¨á¨ ¢ ª®­æ¥ ¤®¯®«­¥­¨ï
//  - ¯®ä¨ªá¥­ £«îª á § ¯¨áìî "GMT" ¢ ¤ â¥ ¤®¯®«­¥­¨ï - íâ® ¡ë« ¤¥­ì ­¥¤¥«¨ ;-)
//  - ¥é¥ à § ¯®ä¨ªá¥­  á¨âã æ¨ï ª®£¤  ¤ ¥âáï ­¥¯à ¢¨«ì­®¥ ¨¬ï ¤®¯®«­¥­¨ï
//
//  - ­ ©¤¥­ ®ç¥à¥¤­®© £«îª ®â ª á¯¥àáª®£®:
//    ¢ ¡¨­ à­®¬ å¥ ¤¥à¥ ª ¤®¯®«­¥­¨î ­ å®¤¨âáï ®¤­® ¢à¥¬ï á®§¤ ­¨ï,
//      ¢ â¥ªáâ®¢ëå ª®¯¨à ©â å ¢ ­ ç «¥ ¤®¯®«­¥­¨ï - ¤àã£®¥.
//    â¥ªáâ®¢®¥ ¢à¥¬ï ®â«¨ç ¥âáï ®â ¡¨­ à­®£® â¥¬, çâ® ç á (hour) ¢ â¥ªáâ¥
//    ã¢¥«¨ç¥­ ­  §­ ç¥­¨¥ dayofweek, ¨§-§  ç¥£® ï ¥£® à ­¥¥ ¨ ¯à¨­ï« §  gmt
//    ­ ¯à¨¬¥à ¢ å¥ ¤¥à¥ "jan-1-99 Mon 12:xx:xx" (¢ § ¯ ª®¢ ­­®© ä®à¬¥),
//      ¢ â¥ªáâ¥ ¡ã¤¥â ­ ¯¨á ­® 13:xx:xx, â.ª. Mon=1
//  - á¨ï ä¨ç  ®ä®à¬«¥­  ¢ ¢¨¤¥ ¢ë¤ ç¨ á®®¡é¥­¨ï â¨¯  "bug with time found"
//  - ¤®¡ ¢«¥­  ¯®¤¤¥à¦ª  AV
//
//AVPX 3.19       26-06-99
//
//  - ¤®¡ ¢«¥­ á®¡áâ¢¥­­® history.txt
//  - ¤®¡ ¢«¥­ ä ©« _del!.bat, ¢ ­¥£® ¤®¡ ¢«ïîâáï â®«ìª® _á®§¤ ­­ë¥_ ä ©«ë
//  - ¨§¬¥­¥­ë ¨¬¥­  á®àæ®¢ëå ®¡¦¥©,   ª®­ªà¥â­¥¥ ã¡à ­®  ­­®ïé¥¥ ç¨á«®:
//       _alicia-b.c.40000.o16 -> _alicia-b.c.o16
//  - ¯®ä¨ªá¥­ ¡ £ á ¢ë¤ ç¥© ª®«-¢  ¨ à §¬¥à  ¢á¥å á®§¤ ­­ëå ä ©«®¢
//    (¢á¥£¤  ãç¨âë¢ «¨áì ­¥ ¢á¥£¤  áâ¨à ¥¬ë¥ .l16/.l32 ä ©«ë),
//  - âã¤  ¦¥ ¤®¡ ¢«¥­  ¢ë¤ ç  ª®«-¢  § ¯¨á¥© ¢ ¤®¯®«­¥­¨¨
//  - ¯®ä¨ªá¥­  ä¨ç  á ­¥¯à ¢¨«ì­ë¬ ¨¬¥­¥¬ ¤®¯®«­¥­¨ï ¢ ª¬¤áâà®ª¥, à ­ìè¥
//    á®§¤ ¢ « áì ¤¨à¥ªâ®à¨ï ¯®â®¬ ¯à®¢¥àª  ­  ¨¬ï ä ©« , â¥¯¥àì ­ ®¡®à®â
//
//¤® á¨å ¨áâ®à¨ï ®âáãâáâ¢®¢ «  ª ª ä ªâ, ¤  ¨ ª®¬ã ®­  ­ åã© ­ã¦­ ...
//
////////x///////x///////x///////x///////x///////x///////x///////x///////x//////

#include <windows.h>

#include <stdio.h>
#include <stdlib.h>
#include <io.h>
#include <string.h>
#include <sys\timeb.h>
#include <dir.h>
#include <dos.h>
#include <assert.h>
#include <conio.h>
#include <time.h>

#pragma hdrstop

#pragma pack(1)

int totalnamecount=0;
int totalfiles=0;
int totalbytes=0;
char outpath[256]="";
char tempdir[256];

int key_max=0;
char* key_arr[256];

struct ftime onclose_ft0;
struct ftime onclose_ft;

int OPT_NOOBJS=0;
int OPT_NOOBJS16=0;
int OPT_NOOBJS32=0;
int OPT_KEEPLIB=0;
int OPT_KEEPLNK=0;
int OPT_NAMES=0;
int OPT_QQ=0;
int OPT_Q=0;
int OPT_A=0;
int OPT_NH=0;
int OPT_NS=0;
int OPT_P=0;
int OPT_REN=0;

void quit(int exitcode)
{
  if (exitcode!=0)
  if (OPT_P)
    getch();
  exit(exitcode);
}

FILE *qd = NULL;
int  qdx = 0;

FILE *FOPEN(const char *filename, const char *mode)
  {
    char temp[256];
    if (mode[0]=='w')
      {
        if (qdx==0)
          totalfiles++;

        if ((qd != NULL) && (qdx == 0))
          fprintf(qd, "del %s\n", filename);
      }
    strcpy(temp, outpath);
    strcat(temp, filename);
    return fopen(temp, mode);
  }

int FCLOSE(FILE *stream)
  {
    fflush(stream);
    if (qdx==0)
      totalbytes += filelength(fileno(stream));
    setftime(fileno(stream), &onclose_ft);
    return fclose(stream);
  }

#define MIN(a, b)       (((a) < (b)) ? (a) : (b))
#define MAX(a, b)       (((a) > (b)) ? (a) : (b))

typedef unsigned char   byte;
typedef unsigned short  word;
typedef unsigned long   dword;

typedef struct
  {
    word        avt_year;
    word        avt_month;
    word        avt_dw;
    word        avt_day;
    word        avt_hour;
    word        avt_min;
    word        avt_sec;
    word        avt_unknown;
  } avtime;

typedef struct
  {
    dword       avc_id;         // EK.8                    00 01 02 03
    word        avc_ver;        // 3                       04 05
    byte        avc_flags;      //                         06
    byte        avc_unk1[5];    // ?                       07 08 09 0A 0B
    dword       avc_filesize;   //                         0C 0D 0E 0F
    dword       avc_sux_offs;   //                         10 11 12 13
    word        avc_sux_count;  //                         14 15
    word        avc_unk2;       // ?  =0                   16 17
    avtime      avc_time1;      //                         18 ... 27
    avtime      avc_time2;      //                         28 ... 37
    byte        avc_unk3[6];    // ?                       38 ... 3d
    dword       avc_author_cs2; //                         3E 3F 40 41
    dword       avc_header_cs1; //                         42 43 44 45
  } avc_header;

typedef struct
  {
    word        sux_type;       // 0/1/2 / 100H            00 01
    word        sux_subtype;    // sub-id                  02 03
    dword       sux_dataoffs;   //                         04 05 06 07
    dword       sux_datasize;   // compressed data size    08 09 0a 0b
    dword       sux_realsize;   // real data size          0c 0d 0e 0f
    word        sux_unk1;       // ? =1                    10 11
    word        sux_recsize;    // record size (or 0)      12 13
    long        sux_recnum;     // records(stamms)         14 15 16 17
                                // or lines(names)
                                // or files(objects)
    dword       sux_data_cs;    //                         18 19 1A 1B
    byte        sux_unused[8];  // ?                       1C ... 23

  } sux_header;

typedef struct
  {
    byte        x1_unk1[15];    // 00 .. 0E
    word        x1_objn;        // 0F 10
    byte        x1_unk2[7];     // 11 .. 17
  } x1_header;

typedef struct
  {
    byte        x2_unk1[11];    // 00 .. 0A
    word        x2_objn;        // 0B 0C
    dword       x2_nameo;       // 0D 0E 0F 10
    byte        x2_unk2[8];     // 11 .. 18
  } x2_header;

typedef struct
  {
    byte        x3_cs1_size;    //               00
    word        x3_cs1_offs;    //               01 02
    word        x3_cs_word;     //               03 04
    dword       x3_cs1_cs;      //               05 06 07 08
    byte        x3_cs2_size;    //               09
    word        x3_cs2_offs;    //               0A 0B
    dword       x3_cs2_cs;      //               0C 0D 0E 0F
    word        x3_objn;        //               10 11
    dword       x3_nameo;       //               12 13 14 15
    byte        x3_unk3[12];    //               17 .. 21
  } x3_header;

typedef struct
  {
    byte        x4_cs1_size;    //               00
    word        x4_cs1_offs;    //               01 02
    word        x4_cs_word;     //               03 04
    byte        x4_flags;       //               05
    dword       x4_cs1_cs;      //               06 07 08 09
    byte        x4_cs2_size;    //               0A
    word        x4_cs2_offs;    //               0B 0C
    dword       x4_cs2_cs;      //               0D 0E 0F 10
    word        x4_objn;        //  or FFFF      11 12
    dword       x4_nameo;       //               13 14 15 16
    byte        x4_unk3[11];    //               17 .. 21
  } x4_header;

typedef struct
  {
    byte        x5_unk1[17];    // 00 .. 10
    word        x5_objn;        // 11 12
    dword       x5_nameo;       // 13 14 15 16
  } x5_header;

typedef struct
  {
    byte        x6_unk1[17];    // 00 .. 10
    word        x6_objn;        // 11 12
    dword       x6_nameo;       // 13 14 15 16
  } x6_header;

typedef struct
  {
    byte        x7_unk1[17];    // 00 .. 10
    word        x7_objn;        // 11 12
    dword       x7_nameo;       // 13 14 15 16
  } x7_header;


char temp_s[256];

char *monthstr[] = {"---", "Jan", "Feb", "Mar", "Apr", "May", "Jun",
                           "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"};

char *dwstr[] =
  {"Sun", "Mon","Tue","Wed","Thu","Fri","Sat","Sun"};

char* avtimestr(const avtime* x)
  {
    char t[32];

#define s temp_s

    strcpy(s, monthstr[x->avt_month]);
    strcat(s, " ");
    strcat(s, itoa(x->avt_day,t,10));
    strcat(s, " ");
    strcat(s, itoa(x->avt_year,t,10));
    strcat(s, ", ");

    strcat(s, dwstr[ x->avt_dw] );
    strcat(s, "  ");

    strcat(s, itoa(x->avt_hour,t,10));
    strcat(s, ":");
    strcat(s, itoa(x->avt_min,t,10));
    strcat(s, ":");
    strcat(s, itoa(x->avt_sec,t,10));
    strcat(s, ".");
    strcat(s, itoa(x->avt_unknown,t,10));

    return s;

#undef s
  }

char* ftimestr(struct ftime* x)
   {
     char t[32];

#define s temp_s

     strcpy(s, monthstr[x->ft_month]);
     strcat(s, " ");
     strcat(s, itoa(x->ft_day, t, 10));
     strcat(s, " ");
     strcat(s, itoa(x->ft_year+1980, t, 10));
     strcat(s, "  ");
     strcat(s, itoa(x->ft_hour, t, 10));
     strcat(s, ":");
     strcat(s, itoa(x->ft_min, t, 10));
     strcat(s, ".");
     strcat(s, itoa(x->ft_tsec * 2, t, 10));

     return s;
#undef s
   }



char fnum_s[5]="xxxx";
int nl_size;

char* fnum(int i)
  {
    fnum_s[0]=i/1000 % 10 + '0';
    fnum_s[1]=i/ 100 % 10 + '0';
    fnum_s[2]=i/  10 % 10 + '0';
    fnum_s[3]=i/   1 % 10 + '0';
    return fnum_s;
  }

char* fname(int k,
            const sux_header h,
            int n,
            int m)
  {
    char t[32];
#define s temp_s

    strcpy(s,"");

    if (k==9)
      {
        strcat(s,"_lnk");
        strcat(s, fnum(h.sux_subtype+1000*m));
        strcat(s,".dat");
        return s;
      }

    if ((k==3)||(k==4))
      {
        strcat(s,"_sux");
        strcat(s,fnum(n));
        if (k==3) strcat(s,".hdr");
        if (k==4) strcat(s,".txt");
        return s;
      }

    if (h.sux_type==0)
      {
        if (h.sux_subtype==0)
          {
            strcat(s,"_ind");
            strcat(s, fnum(n));
            strcat(s,".dat");
            return s;
          }
        else
          {
            strcat(s,"_sta");
            strcat(s, fnum(n));
            strcat(s,".sta");
            return s;
          }
      }

    if ((h.sux_type==0x100)&&(h.sux_subtype==0))
      {
        strcat(s,"_nam");
        strcat(s, fnum(n));
        strcat(s,".nam");
        return s;
      }

    if (k==1)
      {
        if (h.sux_type==1)
          {
            strcat(s,"_lib");
            strcat(s,fnum(n));
            strcat(s,".l16");
            return s;
          }
        if (h.sux_type==2)
          {
            strcat(s,"_lib");
            strcat(s,fnum(n));
            strcat(s,".l32");
            return s;
          }
      }

    if ((k==2)&&((h.sux_type==1)||(h.sux_type==2)))
      {
        strcat(s,"_o");

        if (n<10)
          t[0]=n+'0';
        else
          t[0]=n-10+'a';
        t[1]=0;

        strcat(s,"_");

        strcat(s,t);

        strcat(s,fnum(m));
        if (h.sux_type==1) strcat(s,".o16");
        if (h.sux_type==2) strcat(s,".o32");
        return s;
      }

    strcat(s,"_unk");
    strcat(s,fnum(n));
    strcat(s,".unk");

    return s;

#undef s
  }

void __cdecl unxor(void* s, dword ssize)
  {
    asm
      {
        mov     esi, s
        mov     ecx, ssize
        xor     eax, eax
__1:    xor     [esi], al
        inc     esi
        inc     eax
        loop    __1
      }
  }

dword   __nextbyteptr;
word    __bits;
byte    __len;
dword   __maxin;
dword   __maxout;

dword __cdecl unpack(void* s, void* d, dword ssize, dword dmax)
  {
    asm
      {
        mov     eax, s
        mov     __nextbyteptr, eax

        add     eax, ssize
        mov     __maxin, eax

        mov     edi, d

        mov     eax, edi
        add     eax, dmax
        mov     __maxout, eax

        call    __unp

        sub     edi, d
        xchg    edi, eax

        jmp     __quit

__unp:

        call    __getbyte
        push    eax
        call    __getbyte
        pop     ebx
        mov     ah, bl
        xchg    ah, al
        mov     __bits, ax
        mov     __len, 16

__loc_0_D20:

        call    __get_bit
        or      ax, ax
        jz      __loc_0_D53
        call    __getbyte
        mov     [edi], al
        inc     edi
        cmp     edi, __maxout
        jne     __loc_0_D20
        jmp     __e

__loc_0_D53:

        call    __get_bit
        or      ax, ax
        jnz     __loc_0_D8F

        call    __get_bit
        shl     ax, 1
        mov     si, ax
        call    __get_bit
        or      si, ax
        add     si, 2
        call    __getbyte
        or      ax, 0FF00h
        mov     dx, ax

        jmp     __loc_0_E19

__loc_0_D8F:

        call    __getbyte

__loc_0_DAD:

        mov     ah, 0
        mov     dx, ax
        call    __getbyte

        mov     ah, 0
        mov     si, ax
        and     ax, 0FFF8h
        mov     cl, 5
        shl     ax, cl
        or      ax, 0E000h
        or      dx, ax
        and     si, 7
        add     si, 2
        cmp     si, 2
        jnz     __loc_0_E19
        call    __getbyte

__loc_0_E08:

        mov     ah, 0
        mov     si, ax
        or      si, si
        jz      __e
        cmp     si, 1
        jnz     __loc_0_E18
        jmp     __loc_0_D20

__loc_0_E18:

        inc     si

__loc_0_E19:

        movsx   edx, dx
        add     edx, edi
        jmp     __loc_0_E33

__loc_0_E21:

        mov     ebx, edx
        mov     al, [ebx]
        mov     [edi], al
        inc     edi
        dec     si
        inc     edx
        cmp     edi, __maxout
        ja      __e

__loc_0_E33:

        or      si, si
        jg      __loc_0_E21
        jmp     __loc_0_D20

__e:

        retn

__getbyte:

        push    ebx
        mov     ebx, __nextbyteptr

        cmp     ebx, __maxin
        jae     __sucks

        mov     al, [ebx]
        pop     ebx
        inc     __nextbyteptr
        retn

__sucks:mov     eax, -1
        pop     ebx
        retn

__get_bit:

        mov     dx, __bits
        and     dx, 1
        mov     al, __len
        add     al, -1
        mov     __len, al
        jnz     __shr_XXX

        call    __getbyte
        push    ax
        call    __getbyte
        pop     bx
        mov     ah, bl
        xchg    ah, al
        mov     __bits, ax
        mov     __len, 16
        jmp     __c1

__shr_XXX:

        shr     __bits, 1

__c1:

        mov     ax, dx
        retn


__quit:
    }

    return _EAX;
  }


//
// ­¨¦¥á«¥¤ãîé ï ¯®¤¯à®£à ¬ª  ¯à¥¤áâ ¢«ï¥â ­ ¨¡®«ìè¨© ¨­â¥à¥á ¢® ¢á¥¬ á®àæ¥
//

char nlo[256]="default";

char* __cdecl nl_offs2name(void* nl, dword o)
  {
    if (o>=(unsigned)nl_size) return "";
    asm {

      mov     esi, nl
      add     esi, o

      cld

//    jmp     __r_quit

/*
      mov     eax, nl
      cmp     dword ptr [eax], 'rbiL'
      jne     __r__r

__r_kernel:

      lea     edi, nlo
__r_q:
      lodsb
      stosb
      cmp     al, 0ah
      jne     __r_q
      sub     [edi-1], al
      jmp     __r_quit

__r__r:

*/

;

__r_chknxt:
      cmp     [esi].byte ptr 0, '.'
      je      __r_sux

      cmp     [esi].byte ptr 0, '#'
//    cmp     [esi].word ptr 0, 0A23h
      je      __r_sux

      jmp     __r_ok

__r_sux:

      cmp     esi, nl
      jbe     __r_ok

      dec     esi
      cmp     [esi-1].byte ptr 0, 0Ah
      jne     __r_sux

      jmp     __r_chknxt

__r_ok:

;

      push    esi

      lea     edi, nlo

__r_x_1:
      lodsb
      stosb
      cmp     al, 0ah
      jne     __r_x_1
      sub     [edi-1], al

      pop     esi

;

__r_next:

      mov     edx, esi
      lea     edi, nlo

      cmp     [esi].byte ptr 0, '#'
//    cmp     [esi].word ptr 0, 0A23h
      je      __r_skip_xxx

__r_4:
      cmp     [esi].byte ptr 0, '.'
      jne     __r_2
      inc     esi
__r_3:
      cmp     [edi].byte ptr 0, 0
      jne     __r_2x
      dec     esi
      jmp     __r_2
__r_2x:
      inc     edi
      cmp     [edi].byte ptr -1, '.'
      jne     __r_3
      jmp     __r_4
__r_2:

__r_5:
      lodsb
      stosb
      cmp     al, 0Ah
      jne     __r_5
      sub     [edi-1], al

__r_skip:

      mov     eax, nl
      add     eax, o

      cmp     edx, eax
      jb      __r_next

      mov     esi, nl
      add     esi, o

//    cmp     [esi].word ptr 0, 0A23h
      cmp     [esi].byte ptr 0, '#'
      jne     __r_quit

      lea     edi, nlo

//    cmp     [esi].word ptr 0, 0A23h
      cmp     [edi].byte ptr 0, '#'
      je      __r_quit

      pusha

      inc     esi

__r_nxxx:
      cmp     [esi].byte ptr 0, 32
      je      __r_skp
      cmp     [esi].byte ptr 0, '.'
      jne     __r_oki
__r_skp:
      inc     esi
      jmp     __r_nxxx
__r_oki:

      push    esi
      xor     edx, edx
      dec     edx
__r_k1:
      inc     edx
      lodsb
      cmp     al, 0ah
      jne     __r_k1
      pop     esi

      push    edi
      mov     ecx, -1
      xor     al, al
      repnz   scasb
      neg     ecx
      dec     ecx
      dec     ecx
      pop     edi

      add     edi, ecx
      sub     edi, edx

      mov     ecx, edx
      rep     cmpsb

      popa

      pushf
      xor     al, al
      mov     ecx, -1
      repnz   scasb
      dec     edi
      popf

      jne     __r_111

      mov     ax, '#'
      stosw

      jmp     __r_quit

__r_111:
      movsb     // '#'

__r_111x:
      cmp     [esi].byte ptr 0, 32
      je      __r_2222
      cmp     [esi].byte ptr 0, '.'
      jne     __r_111a
__r_2222:
      inc     esi
      jmp     __r_111x

__r_111a:
      lodsb
      stosb
      cmp     al, 0ah
      jne     __r_111a
      sub     [edi-1], al

      jmp     __r_quit

__r_skip_xxx:

__r_lods:
      lodsb
      cmp     al, 0ah
      jne     __r_lods
      jmp     __r_skip

__r_quit:


    }

//    for (int i=0; i<(signed)strlen(nlo); i++)   // 3.21
//       if ((nlo[i]=='\\')||(nlo[i]=='/')||(nlo[i]<32)||(nlo[i]==':'))
//         nlo[i]='_';

    return nlo;
  }

void unpack_avc(byte* filename)
  {
    FILE* f;
    FILE* o;
    FILE* q;
    FILE* w;
    FILE* e1, *e2;
    FILE* ee;
    FILE* ee2;
    FILE* otd;
    byte cpr[128];
    avc_header avch;
    sux_header suxh;
    dword max_p;
    dword max_u;
    void* arr_p;
    void* arr_u;
    char s[256],s1[256],s2[256],s3[256],s9[256],qw1[256],qw2[256];
    dword l[2];
    byte csum[64];
    int is_csum;
    x1_header x1;
    x2_header x2;
    x3_header x3;
    x4_header x4;
    x5_header x5;
    x6_header x6;
    x7_header x7;
    FILE *nf;
    char nfs[256]="";
    char ss[64],ss2[64],ss3[64];
    int total_stamms=0;

    f = fopen(filename, "rb");
    if (f == NULL)
      {
        if (!OPT_QQ)
        printf("error: %s (%s)\n", _sys_errlist[errno], filename);
        quit(1);
      }

    fread(cpr, 1,sizeof(cpr), f);
    fread(&avch, 1,sizeof(avch), f);

    if ((avch.avc_id&0x00FFFFFF) != 0x002E4B45)
       {
        if (!OPT_QQ)
         printf("error: EK.X format not detected (%s)\n", filename);
         quit(2);
       }
    if (!OPT_Q)
    printf("EK.X format detected\n\n");

    //
    struct ftime ft;
    ft.ft_year  = (avch.avc_time1.avt_year) - 1980;
    ft.ft_month = avch.avc_time1.avt_month;
    ft.ft_day   = avch.avc_time1.avt_day;
    ft.ft_hour  = avch.avc_time1.avt_hour + 3;              // GMT?
    ft.ft_min   = avch.avc_time1.avt_min;
    ft.ft_tsec  = (avch.avc_time1.avt_sec) / 2;
    onclose_ft0 = ft;
    onclose_ft = ft;
    //

/////
    if (access(tempdir,0)==0)
    {
      if (!OPT_Q)
      printf("directory %s alredy exists\n", tempdir);
    }
    else
      {
        if (!OPT_Q)
        printf("creating directory %s\n", tempdir);
        if (mkdir(tempdir)!=0)
          {
        if (!OPT_QQ)
            printf("error: (%s)\n", _sys_errlist[errno]);
            quit(3);
          }
      }
    if (!OPT_Q)
    printf("using output path %s\n\n", outpath);
/////

    if (!OPT_NAMES) {

    assert((qd = FOPEN("_del!.bat","wt"))!=NULL);

    assert((q = FOPEN("_del.bat","wt"))!=NULL);
    fprintf(q, "del _*.*");
    FCLOSE(q);

    assert((w = FOPEN("_map.txt","wt")) != NULL);
    assert((otd = FOPEN("_objtime.txt","wt")) != NULL);

    if (OPT_NOOBJS==0)
    {
    assert((e1 = FOPEN("_objname1.bat","wt")) != NULL);
    assert((e2 = FOPEN("_objname2.bat","wt")) != NULL);
    }

    fprintf(w, "%s\n", filename);

if (!OPT_NH)
{
    q = FOPEN("_cpr.hdr","wb");
    assert(q);
    fwrite(cpr, 1,sizeof(cpr), q);
    FCLOSE(q);

    q = FOPEN("_header.hdr","wb");
    assert(q);
    fwrite(&avch, 1,sizeof(avch), q);
    FCLOSE(q);
}
    fprintf(w, "³ (_map.txt)\n");
    fprintf(w, "³ (_objtime.txt)\n");
    if (OPT_NOOBJS==0)
    {
    fprintf(w, "³ (_objname1.bat)\n");
    fprintf(w, "³ (_objname2.bat)\n");
    }
    if (!OPT_NS)
    fprintf(w, "³ (_stamm.txt)\n");
    fprintf(w, "³ (_names)\n");

    if (!OPT_NH)
    {
    fprintf(w, "ÃÄ _cpr.hdr\n");
    fprintf(w, "ÃÄ _header.hdr (_header.txt)\n");
    }

if (!OPT_NH)
{
    q = FOPEN("_header.txt","wt");
    assert(q);
    fprintf(q, "dump of file %s/_header.hdr\n\n",filename);

    fprintf(q, "structure at 0x%08X\n\n", 0x80);

    fprintf(q, "0000    dword    avc_id         %08X        %c%c%c%c\n",
      avch.avc_id,
      avch.avc_id&255,
      (avch.avc_id>>8)&255,
      (avch.avc_id>>16)&255,
      avch.avc_id>>24);
    fprintf(q, "0004    word     avc_ver        %04X            %i\n", avch.avc_ver, avch.avc_ver);
    fprintf(q, "0006    byte     avc_flags      %04X                  bit0=made NOT in kami\n", avch.avc_flags);
    fprintf(q, "0007    byte[5]  avc_unk1       %02X %02X %02X %02X %02X\n",
      avch.avc_unk1[0],
      avch.avc_unk1[1],
      avch.avc_unk1[2],
      avch.avc_unk1[3],
      avch.avc_unk1[4]);
    fprintf(q, "000C    dword    avc_filesize   0x%08X      %i\n", avch.avc_filesize, avch.avc_filesize);
    fprintf(q, "0010    dword    avc_sux_offs   0x%08X      %i\n", avch.avc_sux_offs, avch.avc_sux_offs);
    fprintf(q, "0014    word     avc_sux_count  0x%04X          %i\n", avch.avc_sux_count, avch.avc_sux_count);
    fprintf(q, "0016    word     avc_unk2       0x%04X          %i\n", avch.avc_unk2, avch.avc_unk2);

    fprintf(q, "0018    byte[16] avc_time1      %s\n", avtimestr(&avch.avc_time1));
    fprintf(q, "0028    byte[16] avc_time2      %s\n", avtimestr(&avch.avc_time2));

    fprintf(q, "0038    byte[6]  avc_unk3       %02X %02X %02X %02X %02X %02X\n",
      avch.avc_unk3[0],
      avch.avc_unk3[1],
      avch.avc_unk3[2],
      avch.avc_unk3[3],
      avch.avc_unk3[4],
      avch.avc_unk3[5]);

    fprintf(q, "003E    dword    avc_cs2        0x%08X\n", avch.avc_author_cs2);
    fprintf(q, "0042    dword    avc_cs1        0x%08X\n", avch.avc_header_cs1);

    fprintf(q, "\ntotal structure size = 0x%02X (%i)\n\n", sizeof(avch), sizeof(avch));

    FCLOSE(q);
}
    if (!OPT_Q)
    printf("file: %s\n", filename);

        if (!OPT_QQ)
    if ((avch.avc_id>>24) != '8')
      printf("warning: file format type is EK.%c instead of EK.8\n", avch.avc_id>>24);

        if (!OPT_QQ)
    if (avch.avc_ver != 3)
      printf("warning: file format version is %i (.AV%c) instead of 3 (.AVC)\n", avch.avc_ver, avch.avc_ver-1+'A');

    if (!OPT_Q)
    {
    printf("\nheader:       size=%-8i time=%s\n", avch.avc_filesize, avtimestr(&avch.avc_time1));
    struct ftime ft;
    getftime(fileno(f), &ft);
    printf("dos reports:  size=%-8i creationtime=%s\n", filelength(fileno(f)), ftimestr(&ft));
    }

    if (!OPT_Q)
    {
    printf("\ninfo:\n");
    printf("  %s\n", cpr);
    printf("  %s\n", cpr+64);

    printf("\n%i datablocks found at 0x%08X\n\n", avch.avc_sux_count, avch.avc_sux_offs);

    printf("##  offs      compsize  realsize  id1  id2   recnum    recsize\n");
    }
}

    max_p = 0;
    max_u = 0;

    for (int a=0; a<avch.avc_sux_count; a++)
      {
        fseek(f, avch.avc_sux_offs + a * sizeof(sux_header), SEEK_SET);
        fread(&suxh, 1,sizeof(suxh), f);

if (!OPT_NAMES) {

  if (!OPT_NH)
  {
        q = FOPEN(fname(3,suxh,a,0),"wb");
        assert(q);
        fwrite(&suxh, 1,sizeof(suxh), q);
        FCLOSE(q);

        q = FOPEN(fname(4,suxh,a,0),"wt");
        assert(q);
        strcpy(s1, fname(3,suxh,a,0));
        strcpy(s2, fname(1,suxh,a,0));
        if (OPT_KEEPLIB==0)
        if ((suxh.sux_type==1)||(suxh.sux_type==2)) strcat(s2, "/ERASED/");

        strcpy(s9, fname(9,suxh,a,suxh.sux_type));

        if ((suxh.sux_type==1) || (suxh.sux_type==2))
          fprintf(w, "ÃÄ %s (%s, %s)  type=%04X subtype=%04X  linkfile=%s\n",s1,s2,fname(4,suxh,a,0), suxh.sux_type,suxh.sux_subtype, s9 );
        else
          fprintf(w, "ÃÄ %s (%s, %s)  type=%04X subtype=%04X\n",s1,s2,fname(4,suxh,a,0), suxh.sux_type,suxh.sux_subtype);

        fprintf(q, "dump of file %s -> %s -> %s\n\n", filename,s1,s2);

        fprintf(q, "structure at 0x%08X\n\n", avch.avc_sux_offs + a * sizeof(sux_header));

        fprintf(q, "0000    word     sux_type       0x%04X\n", suxh.sux_type);
        fprintf(q, "0002    word     sux_subtype    0x%04X\n", suxh.sux_subtype);
        fprintf(q, "0004    dword    sux_dataoffs   0x%08X      %i\n", suxh.sux_dataoffs, suxh.sux_dataoffs);
        fprintf(q, "0008    dword    sux_datasize   0x%08X      %i\n", suxh.sux_datasize, suxh.sux_datasize);
        fprintf(q, "000C    dword    sux_realsize   0x%08X      %i\n", suxh.sux_realsize, suxh.sux_realsize);
        fprintf(q, "0010    word     sux_unk1       0x%04X\n", suxh.sux_unk1);
        fprintf(q, "0012    word     sux_recsize    0x%04X          %i\n", suxh.sux_recsize,suxh.sux_recsize);
        fprintf(q, "0014    dword    sux_recnum     0x%08X      %i\n", suxh.sux_recnum,suxh.sux_recnum);
        fprintf(q, "0018    dword    sux_data_cs    0x%08X\n", suxh.sux_data_cs);
        fprintf(q, "001C    byte[8]  sux_unused     ");
        for (int i=0; i<8; i++)
          fprintf(q, "%02X ", suxh.sux_unused[i]);

        fprintf(q, "\n\ntotal structure size = 0x%02X (%i)\n\n", sizeof(suxh), sizeof(suxh));
        FCLOSE(q);
  }

    if (!OPT_Q)
        printf("%-2i  %08X  %08X  %08X  %04X %04X  %08X",
               a,
               suxh.sux_dataoffs,
               suxh.sux_datasize,
               suxh.sux_realsize,
               suxh.sux_type,
               suxh.sux_subtype,
               suxh.sux_recnum);
        if (suxh.sux_recsize != 0)
    if (!OPT_Q)
        printf("  %04X", suxh.sux_recsize);

    if (!OPT_Q)
        printf("\n");
}

if ( (!OPT_NAMES) || ((suxh.sux_type==0x100)&&(suxh.sux_subtype==0)) )
{
        max_p = MAX(max_p, suxh.sux_datasize);
        max_u = MAX(max_u, suxh.sux_realsize);
}

      }

    if (max_p==0)
    {
        if (!OPT_QQ)
      printf("warning: it seems no fucking names?...\n");
//    quit(4);
    }

if (!OPT_NAMES) {
    if (!OPT_Q){
    printf("\nmaximal   compressed data size %7i byte(s)\n", max_p);
    printf("maximal decompressed data size %7i byte(s)\n", max_u);
    }
}

    if (!OPT_Q)
    printf("allocating %i kb of heap memory\n\n", (max_p+max_u)>>10);

    arr_p=malloc(max_p+1024);
    assert(arr_p);
    arr_u=malloc(max_u+1024);
    assert(arr_u);

if (!OPT_NAMES) {
    if (!OPT_Q)
    printf("unpacking datablocks:\n");
}

    for (int a=0; a<avch.avc_sux_count; a++)
      {
        fseek(f, avch.avc_sux_offs + a * sizeof(sux_header), SEEK_SET);
        fread(&suxh, 1,sizeof(suxh), f);

        if ((suxh.sux_type==0x100)&&(suxh.sux_subtype==0))
          strcpy(nfs, fname(1,suxh,a,0));

if (!OPT_NAMES) {
    if (!OPT_Q)
        printf("%-2i %-12s  %6i --> ", a, fname(1,suxh,a,0), suxh.sux_datasize);
}

if ( (!OPT_NAMES) || ((suxh.sux_type==0x100)&&(suxh.sux_subtype==0)) )
{

        fseek(f, suxh.sux_dataoffs, SEEK_SET);
        fread(arr_p, 1,suxh.sux_datasize, f);

        if (suxh.sux_datasize != 0)  // 3.30
          unxor(arr_p, suxh.sux_datasize);

        if ((avch.avc_flags & 0x00000001) == 0)
          {
            // 3.30
            if (suxh.sux_datasize == 0)
              suxh.sux_realsize = 0;
            if (suxh.sux_realsize != 0)
            {
              dword tt = unpack(arr_p, arr_u, suxh.sux_datasize, max_u);
              if (tt != suxh.sux_realsize)
              {
                printf("***WARNING***: suxh.sux_realsize=%d, unpacked=%d\n", suxh.sux_realsize, tt);
                suxh.sux_realsize = tt;
              }
            }
          }
        else
          {
            memcpy(arr_u, arr_p, suxh.sux_realsize);
          }
}

        nl_size = suxh.sux_realsize;
        if (OPT_NAMES)
        if ((suxh.sux_type==0x100)&&(suxh.sux_subtype==0)) break; // for a

if (!OPT_NAMES)
{

        if ((suxh.sux_type!=0)||(!OPT_NS))
        if ( (!OPT_NOOBJS)||((suxh.sux_type!=1)&&(suxh.sux_type!=2)) )
          fprintf(w, "ÃÄ %s\n", fname(1,suxh,a,0));

   if ((suxh.sux_type!=0)||(!OPT_NS))
   {
        if ((OPT_KEEPLIB==0)&&((suxh.sux_type==1)||(suxh.sux_type==2))) qdx++;
        assert((o = FOPEN(fname(1,suxh,a,0),"wb")) != NULL);
        fwrite(arr_u, 1,suxh.sux_realsize, o);
        FCLOSE(o);
        qdx=0;
   }

    if (!OPT_Q)
        printf("%6i  ", suxh.sux_realsize);

        if ( ((suxh.sux_type==1)&&(OPT_NOOBJS16==0)) ||
             ((suxh.sux_type==2)&&(OPT_NOOBJS32==0)) )
          {
            assert((o = FOPEN(fname(1,suxh,a,0),"rb")) != NULL);
            if (!OPT_KEEPLNK) qdx++;
            assert((ee = FOPEN(fname(9,suxh,a,suxh.sux_type),"wb")) != NULL);
            qdx=0;

            for (int b=0; b<suxh.sux_recnum; b++)
              {
                int j;

                if (((b%100)==0)||(b==suxh.sux_recnum-1))
    if (!OPT_Q)
                  printf("%-05i\x08\x08\x08\x08\x08",b);

                if (fread(&l, 1,8, o)!=8) break;
                l[0]-=8;
                if (fread(arr_u, 1,l[0], o)!=l[0]) break;

//              printf("(%i)",l[0]);
//              if (l[0]==986) __emit__(0xcc);

                s1[0]=0;

                strcpy(s2, fname(2,suxh,a,b));
                strcpy(s2, &s2[2]);
                s2[0]='.';

                memset(s1,0,sizeof(s1));
                memset(s3,0,sizeof(s3));

                strcpy(s3, fname(2,suxh,a,b));
                strcpy(s1, "noname");

                if (suxh.sux_type==1)
                  {
                    asm {
//                    pusha
                      mov     esi, arr_u
                      add     esi, 3
                      cld
                      lodsb
                      movzx   ecx, al
                      and     ecx, 31
                      lea     edi, s1

                      pusha
                      mov     ecx, 32
                      xor     al, al
                      rep     stosb
                      popa

                      jecxz   __aa2
__aa1:                lodsb
                      cmp     al, '\'
                      jne     __aa3
                      mov     al,  '@'
__aa3:                stosb
                      loop    __aa1
__aa2:

                      xor     eax, eax
                      stosb

//                    popa
                    }
                  }

                if (suxh.sux_type==2)
                  {
                    asm {
//                    pusha  // 3.27: presence of this PUSHA doesn't changes the followin [ESP].based arr_u
                      mov     esi, arr_u
                      cld
__x1:                 inc     esi
                      cmp     word ptr [esi], 0FFFEh
                      jne     __x1
                      cmp     dword ptr [esi+2], 01670000h
                      jne     __x1
                      add     esi, 6

                      lea     edi, s1

                      pusha
                      mov     ecx, 32
                      xor     al, al
                      rep     stosb
                      popa


                      mov     ecx, 32
__x2:                 dec     ecx
                      jz      __x2x
                      lodsb
                      or      al, al
                      jz      __x2x

                      cmp     al, '\'
                      jne     __bb3
                      mov     al, '@'
__bb3:
                      stosb
                      jmp     __x2

__x2x:                xor     al, al
                      stosb

//                    popa
                    }
                  }

//              printf("û");

                strcpy(s2, &s2[6]);         //  3.19
                char rens[1024];
                sprintf(rens, "_%s%s", s1,s2);

                //
                int res = key_max == 0 ? 1 : 0;
                char* _s3=strupr(strdup(s3));
                char* _rens=strupr(strdup(rens));
                for (int i=0; i<key_max; i++)
                {
                  if (strstr(_s3, key_arr[i])) res++;
                  if (strstr(_rens, key_arr[i])) res++;
                  if (OPT_NOOBJS==0)
                  {
                    int ll=strlen(key_arr[i]);
                    int n=l[0]-ll;
                    for (int j=0; j<n; j++)
                      if (!memcmp( &((BYTE*)arr_u)[j], key_arr[i], ll))
                      {
                        res++;
                        break;
                      }
                  }
                  if (res) break;
                }
                free(_s3);
                free(_rens);

                if (res)
                {

                  if (qd)
                  fprintf(qd, "del %s\n", OPT_REN ? fname(2,suxh,a,b) : rens);

                  if ((suxh.sux_type==1)||(suxh.sux_type==2))
                  if (OPT_NOOBJS==0)
                    {
                      fprintf(e1, "ren %s %s\n", s3, rens);
                      fprintf(e2, "ren %s %s\n", rens, s3);
                    }

                  fwrite(s3, 1,32, ee);
                  fwrite(s1, 1,32, ee);

                  BYTE* xz = (BYTE*)arr_u;
                  char ssss[1024]="";
                  long ttt = 0;
                  if (OPT_NOOBJS==0)
                  {
                    if (  (xz[0]==0x4C)&&(xz[1]==0x01)   )
                    {
                      ttt = *(long*)&xz[4];
                      strcpy(ssss, ctime(&ttt));
                      ssss[strlen(ssss)-1]=0;
                      fprintf(otd, "%08X  %s  %s (%s)\n", ttt, ssss, fname(2,suxh,a,b), rens);
                    }
                  }

                  if (b==suxh.sux_recnum-1) j='À'; else j='Ã';
                  fprintf(w, "³   %cÄ %s (%s)\n",j,s3,s1);

                  if (OPT_NOOBJS==0)
                    {
                      assert((q = FOPEN( OPT_REN ? rens : fname(2,suxh,a,b)
                                        , "wb")) != NULL);
                      fwrite(arr_u, 1,l[0], q);
                      // 3.28
                      if ((ttt!=0)&&(ttt!=-1))
                      {
                        struct ftime ft;
                        struct tm* tm = localtime(&ttt);
                        ft.ft_year  = (tm->tm_year+1900) - 1980;
                        ft.ft_month = tm->tm_mon;
                        ft.ft_day   = tm->tm_mday;
                        ft.ft_hour  = tm->tm_hour;
                        ft.ft_min   = tm->tm_min;
                        ft.ft_tsec  = tm->tm_sec / 2;
                        onclose_ft = ft;
                      }
                      //
                      FCLOSE(q);
                      onclose_ft = onclose_ft0;
                    }

                }//res
              }

            fclose(o);
            if (!OPT_KEEPLNK) qdx++;
            FCLOSE(ee);
            qdx=0;

          }

    if (!OPT_Q)
        printf("\n");
}

      }

/////////////////////////////////////////////////////////////////////////////
    if (!OPT_NAMES) {
/////////////////////////////////////////////////////////////////////////////

    fseek(f, avch.avc_filesize-64, SEEK_SET);   // filelength(fileno(f))
    fread(csum, 1,64, f);

    is_csum = ( (csum[0]==0x0D) && (csum[1]==0x0A) && (csum[2]==';') );

    if (is_csum)
      {
        if (!OPT_NH)
        {
        assert((q = FOPEN("_csum.dat","wb")) != NULL);
        fwrite(csum, 1,64, q);
        FCLOSE(q);
        fprintf(w, "ÀÄ _csum.dat\n");
        }
     }

    FCLOSE(otd);
    FCLOSE(w);
    if (OPT_NOOBJS==0)
    {
      FCLOSE(e1);
      FCLOSE(e2);
    }

    // read names

    nf = FOPEN(nfs,"rb");
    if (nf)
    {
      nl_size = fread(arr_u, 1,max_u, nf);
      fclose(nf);
    }
    else
    nl_size = 0;

    if (!OPT_Q)
    printf("\n");
/////////////////////////////////////////////////////////////////////////////
    }
/////////////////////////////////////////////////////////////////////////////

    if (!OPT_Q)
    printf("writing name list...\n");

    if (!OPT_A)
    assert((q = FOPEN("_names","wt")) != NULL);
    else
    assert((q = FOPEN("_names","at")) != NULL);


    int j=0, namecount=0;
    for (int i=0; i<nl_size; i++)
    {
      if (j==0)
      {
        if (((char*)arr_u)[i]=='#')
        {
//        printf("<%s>\n",nl_offs2name(arr_u,i));
        }
        else
        {
          strcpy(s9, nl_offs2name(arr_u,i));

          int res= key_max==0?1:0;
          char* _s9 = strupr(strdup(s9));
          for (int i=0; i<key_max; i++)
          {
            if (strstr(_s9, key_arr[i]))
            {
              res++;
              break;
            }
          }
          free(_s9);

          if (res)
          {
            fprintf(q, "%s\n", s9);

            namecount++;
            totalnamecount++;
          }
        }
      }

      if (((char*)arr_u)[i]==0x0A) j=0; else j++;
    }
    FCLOSE(q);

    if (!OPT_Q)
    printf("done, %i virii names%s\n", namecount, key_max==0?"":", ***KEYWORDS USED***");

/////////////////////////////////////////////////////////////////////////////
    if (!OPT_NAMES) {
/////////////////////////////////////////////////////////////////////////////

if (!OPT_NS)
{
    if (!OPT_Q)
    printf("\nwriting stamm info list\n");

    assert((q = FOPEN("_stamm.txt","wt")) != NULL);

    if (!OPT_Q)
    {
      if (key_max)
        fprintf(q, "*** KEYWORDS USED ***\n");
      fprintf(q, "stamm dump of file %s\n", filename);
    }

    for (int a=0; a<avch.avc_sux_count; a++)
      {

        fseek(f, avch.avc_sux_offs + a * sizeof(sux_header), SEEK_SET);
        fread(&suxh, 1,sizeof(suxh), f);

        if ((suxh.sux_type==0)&&(suxh.sux_subtype>0))
          {
          if (!OPT_Q)
            printf("  %s  ", fname(2,suxh,a,0));

            strcpy(s9, fname(9,suxh,a,suxh.sux_type));
            fprintf(q, "\nsubtype=0x%04X  recsize=0x%02X  recnum=0x%04X  file=%s  linkfile=%s\n\n",
              suxh.sux_subtype,
              suxh.sux_recsize,
              suxh.sux_recnum,
              fname(2,suxh,a,0),
              s9);

            total_stamms += suxh.sux_recnum;

            if (suxh.sux_subtype>7)
              {
        if (!OPT_QQ)
                printf("warning: unknown subtype (0x%04X)\n", suxh.sux_subtype);
                fprintf(q, "unknown subtype\n\n");
              }
            else
              {

                w = FOPEN(fname(2,suxh,a,0),"rb");
                assert(w);

                strcpy(qw1, fname(9,suxh,a,1));
                strcpy(qw2, fname(9,suxh,a,2));

                ee  = FOPEN(qw1,"rb");
                ee2 = FOPEN(qw2,"rb");

//              if (ee ==NULL) printf(" (%s==NULL) ",qw1);
//              if (ee2==NULL) printf(" (%s==NULL) ",qw2);

                int i;

                for (int j=0; j<suxh.sux_recnum; j++)
                  {

                    if (((j%100)==0)||(j==suxh.sux_recnum-1))
    if (!OPT_Q)
                      printf("%-05i\x08\x08\x08\x08\x08",j);

                    if (suxh.sux_subtype==1) i=fread(&x1, 1,sizeof(x1), w);
                    if (suxh.sux_subtype==2) i=fread(&x2, 1,sizeof(x2), w);
                    if (suxh.sux_subtype==3) i=fread(&x3, 1,sizeof(x3), w);
                    if (suxh.sux_subtype==4) i=fread(&x4, 1,sizeof(x4), w);
                    if (suxh.sux_subtype==5) i=fread(&x5, 1,sizeof(x5), w);
                    if (suxh.sux_subtype==6) i=fread(&x6, 1,sizeof(x6), w);
                    if (suxh.sux_subtype==7) i=fread(&x7, 1,sizeof(x7), w);
                    if (i==0) break;

                    int k=-1;
    //              if (suxh.sux_subtype==1) k = x1.x1_nameo;
                    if (suxh.sux_subtype==2) k = x2.x2_nameo;
                    if (suxh.sux_subtype==3) k = x3.x3_nameo;
                    if (suxh.sux_subtype==4) k = x4.x4_nameo;
                    if (suxh.sux_subtype==5) k = x5.x5_nameo;
                    if (suxh.sux_subtype==6) k = x6.x6_nameo;
                    if (suxh.sux_subtype==7) k = x7.x7_nameo;

                    s[0]=0;
                    if (k!=-1)
                    if (k<(signed)max_u)
                      {
                        strcpy(s, nl_offs2name(arr_u, k));
                      }

                    int z=-1;
                    if (suxh.sux_subtype==1) z = x1.x1_objn;
                    if (suxh.sux_subtype==2) z = x2.x2_objn;
                    if (suxh.sux_subtype==3) z = x3.x3_objn;
                    if (suxh.sux_subtype==4) z = x4.x4_objn;
                    if (suxh.sux_subtype==5) z = x5.x5_objn;
                    if (suxh.sux_subtype==6) z = x6.x6_objn;
                    if (suxh.sux_subtype==7) z = x7.x7_objn;
                    if (z==0xFFFF) z=-1;

                    strcpy(ss ,"");
                    strcpy(ss2,"");
                    strcpy(ss3,"");
                    if (z!=-1)
                      {
                        if (ee !=NULL)  fseek(ee, 64*z, SEEK_SET);
                        if (ee !=NULL)  fread(ss, 1,32, ee);
                        if (ee !=NULL)  fread(ss2, 1,32, ee);

                        if (ee2!=NULL)  fseek(ee2, 64*z, SEEK_SET);
                        if (ee2!=NULL)  fread(ss3, 1,32, ee2);
                      }

                    int res = (key_max == 0 ? 1 : 0);
                    char* _ss=strupr(strdup(ss));
                    char* _ss3=strupr(strdup(ss3));
                    char* _ss2=strupr(strdup(ss2));
                    char* _s=strupr(strdup(s));
                    for (int i=0; i<key_max; i++)
                    {
                      if (strstr(_ss,  key_arr[i])) res++;
                      if (strstr(_ss3, key_arr[i])) res++;
                      if (strstr(_ss2, key_arr[i])) res++;
                      if (strstr(_s,   key_arr[i])) res++;
                      if (res) break;
                    }
                    free(_ss);
                    free(_ss3);
                    free(_ss2);
                    free(_s);

                    if (res)
                    {

                      if (suxh.sux_subtype==1)
                        {
                          fprintf(q, "N=%-5i objn=%04X unk1=%02X %02X %02X %02X  %02X %02X %02X %02X  %02X %02X %02X %02X  %02X %02X %02X    unk3=%02X %02X %02X %02X  %02X %02X %02X  obj=%s/%s(%s) name=%s\n",
                            j,
                            x1.x1_objn,

                            x1.x1_unk1[0],
                            x1.x1_unk1[1],
                            x1.x1_unk1[2],
                            x1.x1_unk1[3],

                            x1.x1_unk1[4],
                            x1.x1_unk1[5],
                            x1.x1_unk1[6],
                            x1.x1_unk1[7],

                            x1.x1_unk1[8],
                            x1.x1_unk1[9],
                            x1.x1_unk1[10],
                            x1.x1_unk1[11],

                            x1.x1_unk1[12],
                            x1.x1_unk1[13],
                            x1.x1_unk1[14],

                            x1.x1_unk2[0],
                            x1.x1_unk2[1],
                            x1.x1_unk2[2],
                            x1.x1_unk2[3],
                            x1.x1_unk2[4],
                            x1.x1_unk2[5],
                            x1.x1_unk2[6],

                            ss,ss3,ss2,s);
                        }

                      if (suxh.sux_subtype==2)
                        {
                          fprintf(q, "N=%-5i objn=%04X nameo=%08X  obj=%s/%s(%s) name=%s\n",
                            j,
                            x2.x2_objn,
                            x2.x2_nameo,
                            ss,ss3,ss2,s);
                        }

                      if (suxh.sux_subtype==3)
                        {
                          fprintf(q, "N=%-5i objn=%04X nameo=%08X word=%04X  cs1=(%04X,%02X,%08X) cs2=(%04X,%02X,%08X) unk3=%02X %02X %02X %02X  %02X %02X %02X %02X  %02X %02X %02X %02X obj=%s/%s(%s) name=%s\n",
                            j,
                            x3.x3_objn,
                            x3.x3_nameo,
                            x3.x3_cs_word,

                            x3.x3_cs1_offs,
                            x3.x3_cs1_size,
                            x3.x3_cs1_cs,

                            x3.x3_cs2_offs,
                            x3.x3_cs2_size,
                            x3.x3_cs2_cs,

                            x3.x3_unk3[0],
                            x3.x3_unk3[1],
                            x3.x3_unk3[2],
                            x3.x3_unk3[3],

                            x3.x3_unk3[4],
                            x3.x3_unk3[5],
                            x3.x3_unk3[6],
                            x3.x3_unk3[7],

                            x3.x3_unk3[8],
                            x3.x3_unk3[9],
                            x3.x3_unk3[10],
                            x3.x3_unk3[11],

                            ss,ss3,ss2,s);
                        }

                      if (suxh.sux_subtype==4)
                        {
                          fprintf(q, "N=%-5i objn=%04X nameo=%08X word=%04X cs1=(%04X,%02X,%08X) cs2=(%04X,%02X,%08X) flags=%02X unk3=%02X %02X %02X %02X  %02X %02X %02X %02X  %02X %02X %02X obj=%s/%s(%s) name=%s\n",
                            j,
                            x4.x4_objn,
                            x4.x4_nameo,
                            x4.x4_cs_word,

                            x4.x4_cs1_offs,
                            x4.x4_cs1_size,
                            x4.x4_cs1_cs,

                            x4.x4_cs2_offs,
                            x4.x4_cs2_size,
                            x4.x4_cs2_cs,

                            x4.x4_flags,

                            x4.x4_unk3[0],
                            x4.x4_unk3[1],
                            x4.x4_unk3[2],
                            x4.x4_unk3[3],

                            x4.x4_unk3[4],
                            x4.x4_unk3[5],
                            x4.x4_unk3[6],
                            x4.x4_unk3[7],

                            x4.x4_unk3[8],
                            x4.x4_unk3[9],
                            x4.x4_unk3[10],

                            ss,ss3,ss2,s);

                        }

                      if (suxh.sux_subtype==5)
                        {
                          fprintf(q, "N=%-5i objn=%04X nameo=%08X  obj=%s/%s(%s) name=%s\n",
                            j,
                            x5.x5_objn,
                            x5.x5_nameo,
                            ss,ss3,ss2,s);
                        }

                      if (suxh.sux_subtype==6)
                        {
                          fprintf(q, "N=%-5i objn=%04X nameo=%08X unk1=%02X %02X %02X %02X  %02X %02X %02X %02X  %02X %02X %02X %02X  %02X %02X %02X %02X  %02X   obj=%s/%s(%s) name=%s\n",
                            j,
                            x6.x6_objn,
                            x6.x6_nameo,
                            x6.x6_unk1[0],
                            x6.x6_unk1[1],
                            x6.x6_unk1[2],
                            x6.x6_unk1[3],

                            x6.x6_unk1[4],
                            x6.x6_unk1[5],
                            x6.x6_unk1[6],
                            x6.x6_unk1[7],

                            x6.x6_unk1[8],
                            x6.x6_unk1[9],
                            x6.x6_unk1[10],
                            x6.x6_unk1[11],

                            x6.x6_unk1[12],
                            x6.x6_unk1[13],
                            x6.x6_unk1[14],
                            x6.x6_unk1[15],

                            x6.x6_unk1[16],

                            ss,ss3,ss2,s);
                        }

                      if (suxh.sux_subtype==7)
                        {
                          fprintf(q, "N=%-5i objn=%04X nameo=%08X unk1=%02X %02X %02X %02X  %02X %02X %02X %02X  %02X %02X %02X %02X  %02X %02X %02X %02X  %02X   obj=%s/%s(%s) name=%s\n",
                            j,
                            x7.x7_objn,
                            x7.x7_nameo,
                            x7.x7_unk1[0],
                            x7.x7_unk1[1],
                            x7.x7_unk1[2],
                            x7.x7_unk1[3],

                            x7.x7_unk1[4],
                            x7.x7_unk1[5],
                            x7.x7_unk1[6],
                            x7.x7_unk1[7],

                            x7.x7_unk1[8],
                            x7.x7_unk1[9],
                            x7.x7_unk1[10],
                            x7.x7_unk1[11],

                            x7.x7_unk1[12],
                            x7.x7_unk1[13],
                            x7.x7_unk1[14],
                            x7.x7_unk1[15],

                            x7.x7_unk1[16],

                            ss,ss3,ss2,s);
                        }

                    }//res

                  } // for each stamm
                if (!OPT_Q)
                printf("\n");

                fclose(w);

                if (ee2!=NULL) fclose(ee2);
                if (ee !=NULL) fclose(ee);

              }

          } // sux_type==0...

      }


    fprintf(q, "\ntotal: %i database records (not viruses!)\n", total_stamms);
    FCLOSE(q);
}

    if (!OPT_KEEPLIB)
      {
//      if (!OPT_Q)
//      printf("\n");
        for (int a=0; a<avch.avc_sux_count; a++)
          {
            fseek(f, avch.avc_sux_offs + a * sizeof(sux_header), SEEK_SET);
            fread(&suxh, 1,sizeof(suxh), f);

            if ((suxh.sux_type==1)||(suxh.sux_type==2))
              {
                strcpy(s2,outpath);
                strcat(s2,fname(1,suxh,a,0));
                remove(s2);
/*              int done=(remove(s2)==0);
        if (!OPT_Q)
        {
                printf("erasing %s: ",fname(1,suxh,a,0));
                if (done)
                  printf("done\n");
                else
                  printf("%s\n", _sys_errlist[errno]);
        }
*/
              }
          }
      }

    if (!OPT_KEEPLNK)
    {
      for (int a=0; a<avch.avc_sux_count; a++)
      {
        fseek(f, avch.avc_sux_offs + a * sizeof(sux_header), SEEK_SET);
        fread(&suxh, 1,sizeof(suxh), f);
        strcpy(s9, outpath);
        strcat(s9, fname(9,suxh,a,suxh.sux_type));
        remove(s9);
/*      int done = (remove(s9)==0);
        if (!OPT_Q)
        {
                printf("erasing %s: ",fname(9,suxh,a,suxh.sux_type));
                if (done)
                  printf("done\n");
                else
                  printf("%s\n", _sys_errlist[errno]);
        }
*/
      }
    }

/////////////////////////////////////////////////////////////////////////////
    }
/////////////////////////////////////////////////////////////////////////////

    fclose(f);

if (!OPT_NAMES) {

    fprintf(qd, "del _del!.bat");        //  w/o "\n" !
    FCLOSE(qd);

    if (!OPT_Q)
    for (int i=0; i<128; i++)   // 01:34:67
      if (cpr[i+2]==':')
      if (cpr[i+5]==':')
        {
          int j = ( (cpr[i]-'0')*10+cpr[i+1]-'0' ) - avch.avc_time2.avt_hour;

          if (j != 0)
            printf("\nGMT=%i, dw=%i\n",
               j,
               avch.avc_time2.avt_dw);

          break;
        }

    if (!OPT_Q)
    printf("\ndone, %i files/%i bytes/%i records\n\n", totalfiles, totalbytes, total_stamms);
}

  }

void help(void)
  {
if (!OPT_Q){
    textattr(0x07);
    cprintf("syntax:\r\n");
    cprintf("  AVPX [option[-] ...] [!keyword ...] filemask[.AVC] [outpath[\\]]\r\n\r\n");
    cprintf("options:\r\n");
    textattr(0x03);cprintf("  /no    ");textattr(0x07);cprintf("...do not create obj files (both 16 and 32-bit) -- works faster\r\n");
    textattr(0x03);cprintf("  /no16  ");textattr(0x07);cprintf("...do not create only 16-bit obj files\r\n");
    textattr(0x03);cprintf("  /no32  ");textattr(0x07);cprintf("...do not create only 32-bit obj files\r\n");
    textattr(0x03);cprintf("  /l     ");textattr(0x07);cprintf("...keep obj libs (.l16/.l32) files -- do not erase 'em on exit\r\n");
    textattr(0x03);cprintf("  /k     ");textattr(0x07);cprintf("...keep lnkNNNN.dat files\r\n");
    textattr(0x03);cprintf("  /names ");textattr(0x07);cprintf("...extract ONLY virii names\r\n");
    textattr(0x03);cprintf("  /a     ");textattr(0x07);cprintf("...append to _names instead of overwriting file\r\n");
    textattr(0x03);cprintf("  /q     ");textattr(0x07);cprintf("...be quiet (but show warnings/errors)\r\n");
    textattr(0x03);cprintf("  /qq    ");textattr(0x07);cprintf("...be quiet (show nothing)\r\n");
    textattr(0x03);cprintf("  /nh    ");textattr(0x07);cprintf("...no headers/info\r\n");
    textattr(0x03);cprintf("  /ns    ");textattr(0x07);cprintf("...no stamms/info\r\n");
    textattr(0x03);cprintf("  /p     ");textattr(0x07);cprintf("...pause on error/warning messages\r\n");
    textattr(0x03);cprintf("  /ren   ");textattr(0x07);cprintf("...automatically rename .OBJ files\r\n");
    printf("\r\n");
    cprintf("examples:\r\n");
    textattr(0x03);cprintf("  AVPX c:\\avp\\* d:\\sux /names /a  ");textattr(0x07);cprintf("...append all known virnames to d:\\sux\\_names\r\n");
    textattr(0x03);cprintf("  AVPX . ");textattr(0x07);cprintf("...will extract all AVCs in the current directory\r\n");
}
    quit(5);
  }

int procswitch(char* s)
{
  if (s[0]!='/') return 0;

  if (stricmp(&s[1],"q" )==0) ; else
  if (stricmp(&s[1],"q-" )==0) ; else
  if (stricmp(&s[1],"qq" )==0) ; else
  if (stricmp(&s[1],"qq-" )==0) ; else
  if (stricmp(&s[1],"p" )==0) ; else
  if (stricmp(&s[1],"p-" )==0) ; else

  if (stricmp(&s[1],"no")==0) OPT_NOOBJS=1;  else
  if (stricmp(&s[1],"no-")==0) OPT_NOOBJS=0;  else
  if (stricmp(&s[1],"no16")==0) OPT_NOOBJS16=1;  else
  if (stricmp(&s[1],"no16-")==0) OPT_NOOBJS16=0;  else
  if (stricmp(&s[1],"no32")==0) OPT_NOOBJS32=1;  else
  if (stricmp(&s[1],"no32-")==0) OPT_NOOBJS32=0;  else
  if (stricmp(&s[1],"l" )==0) OPT_KEEPLIB=1; else
  if (stricmp(&s[1],"l-" )==0) OPT_KEEPLIB=0; else
  if (stricmp(&s[1],"k" )==0) OPT_KEEPLNK=1; else
  if (stricmp(&s[1],"k-" )==0) OPT_KEEPLNK=0; else
  if (stricmp(&s[1],"names" )==0) OPT_NAMES=1; else
  if (stricmp(&s[1],"names-" )==0) OPT_NAMES=0; else
  if (stricmp(&s[1],"a" )==0) OPT_A=1; else
  if (stricmp(&s[1],"a-" )==0) OPT_A=0; else
  if (stricmp(&s[1],"nh" )==0) OPT_NH=1; else
  if (stricmp(&s[1],"nh-" )==0) OPT_NH=0; else
  if (stricmp(&s[1],"ren" )==0) OPT_REN=1; else
  if (stricmp(&s[1],"ren-" )==0) OPT_REN=0; else
  if (stricmp(&s[1],"ns" )==0) OPT_NS=1; else
  if (stricmp(&s[1],"ns-" )==0) OPT_NS=0; else return 0;
  return 1;
}

char aname[256]="";

void procopt(char* s)
{
//  if ((s[0]=='"') && (s[strlen(s)-1]=='"'))
//  {
//    s[strlen(s)-1]=0;
//    s++;
//  }

        if (stricmp(s,"?")==0) help();
        if (stricmp(s,"/?")==0) help();
        if (stricmp(s,"-?")==0) help();
        if (stricmp(s,"/h")==0) help();
        if (stricmp(s,"-h")==0) help();
        if (stricmp(s,"/help")==0) help();
        if (stricmp(s,"-help")==0) help();
        if (stricmp(s,"help")==0) help();

        if (s[0]=='/')
        {
          if (!procswitch(s))
          {
        if (!OPT_QQ)
            printf("error: unknown option (%s)\n", s);
            quit(6);
          }
        }
        else
        if ( (s[0]=='!')&&(s[1]!=0) )
        {
          key_arr[ key_max++ ] = strupr( strdup( &s[1] ) );
        }
        else
          {
            if (aname[0]  ==0) strcpy(aname,  s); else
            if (outpath[0]==0) strcpy(outpath,s); else
              {
        if (!OPT_QQ)
                printf("error: too many command line parameters (%s)\n", s);
                quit(7);
              }
          }

}

void dump_opt()
{
  if (!OPT_Q)
  {
     if (OPT_NAMES)    printf("þ generate names only\n"); else
     if (OPT_A)        printf("þ append names\n");
     if (OPT_NOOBJS)   printf("þ NO 16/32-bit obj-files\n"); else
     {
     if (OPT_NOOBJS16) printf("þ NO 16-bit obj-files\n");
     if (OPT_NOOBJS32) printf("þ NO 32-bit obj-files\n");
     }
     if (OPT_NH)       printf("þ NO headers/info\n");
     if (OPT_NS)       printf("þ NO stamms/info\n");
     if (OPT_KEEPLIB)  printf("þ keep libraries\n");
     if (OPT_KEEPLNK)  printf("þ keep .LNK-files\n");
     printf("\n");
  }
}

void main(int argc, char* argv[])
  {
///////
    for (int i=1; i<argc; i++)
        if (argv[i][0]=='/')
        {
            if (stricmp(&argv[i][1],"q" )==0) OPT_Q=1;
            if (stricmp(&argv[i][1],"q-" )==0) OPT_Q=0;
            if (stricmp(&argv[i][1],"qq" )==0) { OPT_Q=1; OPT_QQ=1; };
            if (stricmp(&argv[i][1],"qq-" )==0) { OPT_Q=0; OPT_QQ=0; };
            if (stricmp(&argv[i][1],"p" )==0) OPT_P=1;
            if (stricmp(&argv[i][1],"p-" )==0) OPT_P=0;
        }
////////

    if (                                                    // av support ;-)
       (fopen("E:\\Avp32\\GK95\\AVP95.pdb","rb")!=NULL) ||
       (fopen("E:\\Avp32\\AVP_IO\\AVP_IO.pdb","rb")!=NULL) ||
       (fopen("E:\\KEHITYS\\JAZZ\\GK95\\GK95.pdb","rb")!=NULL)
       )
      {
        if (!OPT_QQ)
        printf("fuck off!\n");
        quit(8);
      }

if (!OPT_Q)
{
    textattr(0x1F);
    cprintf(" AVPX  AVP eXtender  ");
    textattr(0x1E);
    cprintf("release 3.30");
    textattr(0x1F);
    cprintf("  (x) 1998-2003 Z0MBiE  http://z0mbie.host.sk ");
    textattr(0x07);
    cprintf("\r\n\r\n");
}

    char d[300],p[300],n[300],e[300],q[512],s[512];

    fnsplit(argv[0],d,p,n,e);
    fnmerge(q,d,p,"AVPX.CFG",0);

    FILE*f=fopen(q,"rb");
    if (f!=NULL)
    {
      while (!feof(f))
      {
        fgets(s,sizeof(s),f);
        char*c = &s[0];
        while ((*c==32)||(*c==9)) c++;
        while ((c[strlen(c)-1]==32)||
               (c[strlen(c)-1]==9)||
               (c[strlen(c)-1]==0x0D)||
               (c[strlen(c)-1]==0x0A)
              ) *(short*)&c[strlen(c)-1]=0;
        if ((c[0]!=0)&&(c[0]!=';'))
        {
//        printf("<%s>\n",c);
          procopt(c);
        }
      }
      fclose(f);
    }

    for (int i=1; i<argc; i++)
      procopt(argv[i]);

    OPT_NOOBJS |= (OPT_NOOBJS16!=0)&&(OPT_NOOBJS32!=0);
    if (OPT_NOOBJS)
    {
    OPT_NOOBJS16++;
    OPT_NOOBJS32++;
    }



    if (aname[0]==0) help();

    if (strchr(aname,'.')==NULL) strcat(aname,".avc");

    if (outpath[0]!=0)
      {
        int i = strlen(outpath);

        if ( (i!=0)&&(!((i==2)&&(outpath[1]==':'))) )
          {
            if (outpath[i-1] != '\\')
              {
                strcat(outpath,"\\");
//              outpath[i] = '\\';
//              outpath[i+1] = 0;
              }
          }
      }

//  unpack_avc(aname);

  fnsplit(aname, d,p,n,e);
  if (n[0]==0) strcpy(n,"*");
  if (e[0]==0) strcpy(e,".AVC");
  fnmerge(aname, d,p,n,e);

if (!OPT_QQ)
{
  int pause=0;
  if (outpath[0]!=0)
  if (strchr(aname,'?')||
      strchr(aname,'*'))
  {
    if (!OPT_NAMES)
    {
      printf("warning: you're about to extract more than 1 AVC file into the same directory\n");
      pause++;
    }
    if ((OPT_NAMES)&&(!OPT_A))
    {
      printf("warning: you're about to extract more than 1 virii namelist into the same file(directory), but /a (append) option is not specified\n");
      pause++;
    }
  }
  if (OPT_P)
  if (pause)
  {
      printf("press any fucking key to continue...\n");
      getch();
  }
}

  if (!OPT_Q)
  if (strchr(aname,'?')||strchr(aname,'*'))
  printf("searching for %s\n",aname);

  int filecount=0;

  char* mask = strdup(aname);

  struct ffblk ffblk;
  for (int done=findfirst(mask,&ffblk,FA_ARCH|FA_DIREC); !done; done=findnext(&ffblk))
  {
    if (!(ffblk.ff_attrib&FA_DIREC))
    {
      fnmerge(aname, d,p,ffblk.ff_name,0);
      int killout=0;

//////////
      if (outpath[0]==0)
        {
          killout++;

          strcpy(tempdir,aname);
          if (strrchr(tempdir,'\\')!=0)
            strcpy(tempdir,strrchr(tempdir,'\\')+1);
          if (strrchr(tempdir,'.')!=NULL)
              *strrchr(tempdir,'.')=0;
          strcpy(outpath,tempdir);
          strcat(outpath,"\\");
        }
      else
        {
          strcpy(tempdir,outpath);
          tempdir[strlen(tempdir)-1]=0;
        }
///////

      totalfiles=0;
      totalbytes=0;
      qdx=0;

//    printf("processing %s, outpath=%s tempdir=%s killout=%i\n",aname,outpath,tempdir,killout);

      if (filecount==0)
        dump_opt();

  if (!OPT_Q)
      printf("processing %s\n\n",aname);

      unpack_avc(aname);
      filecount++;

      if (killout) {
        outpath[0]=0;
        tempdir[0]=0;
      }
    }
  }

  if (!OPT_Q)
  if (filecount>1)
  {
    printf("\ntotal: %i files, %i virii names\n", filecount, totalnamecount);
  }

  if (!OPT_Q)
  if (filecount==0)
  {
    printf("file(s) not found\n");
    quit(9);
  }

  quit(0);
}//main
