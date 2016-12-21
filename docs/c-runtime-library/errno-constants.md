---
title: "errno 定数 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ENOEXEC"
  - "ENOMEM"
  - "E2BIG"
  - "STRUNCATE"
  - "ENOENT"
  - "EMFILE"
  - "EBADF"
  - "EDEADLOCK"
  - "EXDEV"
  - "EILSEQ"
  - "EINVAL"
  - "EDOM"
  - "EACCES"
  - "ERANGE"
  - "ENOSPC"
  - "EAGAIN"
  - "EEXIST"
  - "ECHILD"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "E2BIG 定数"
  - "EACCES 定数"
  - "EAGAIN 定数"
  - "EBADF 定数"
  - "ECHILD 定数"
  - "EDEADLOCK 定数"
  - "EDOM 定数"
  - "EEXIST 定数"
  - "EILSEQ 定数"
  - "EINVAL 定数"
  - "EMFILE 定数"
  - "ENOENT 定数"
  - "ENOEXEC 定数"
  - "ENOMEM 定数"
  - "ENOSPC 定数"
  - "ERANGE 定数"
  - "errno 定数"
  - "EXDEV 定数"
  - "STRUNCATE 定数"
ms.assetid: 47089258-d5a5-4cd8-b193-223894dea0cf
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# errno 定数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 構文  
  
```  
  
#include <errno.h>  
```  
  
## 解説  
 **errno** 値は、各種エラーが発生したときに [errno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) 変数に割り当てられる定数です。  
  
 ERRNO.H には、**errno** 値が定義されています。  ただし、ERRNO.H に指定されているすべての定義が 32 ビット Windows オペレーティング システムで使用されるわけではありません。  ERRNO.H の値の一部は、UNIX 系のオペレーティング システムとの互換性を目的としています。  
  
 32 ビット Windows オペレーティング システムの **errno** 値は、XENIX システムの **errno** 値のサブセットです。  したがって、**errno** 値は、Windows オペレーティング システムのシステム コールが返す実際のエラー コードと必ずしも同じとは限りません。  実際のオペレーティング システムのエラー コードにアクセスするには、この値を含む [\_doserrno](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md) 変数を使用します。  
  
 次の **errno** 値がサポートされています。  
  
 **ECHILD**  
 子プロセスが存在しない。  
  
 **EAGAIN**  
 これ以上プロセスを生成できない。  これ以上プロセス スロットが足りないか、メモリが不足か、または最大の入れ子レベルに達したために、新しいプロセスの生成に失敗します。  
  
 **E2BIG**  
 引数リストが長すぎる。  
  
 **EACCES**  
 アクセス許可が拒否された。  ファイルのアクセス権の設定により、指定されたアクセスができません。  このエラーは、ファイルまたはディレクトリにアクセスしたときのモードが、ファイルまたはディレクトリの属性に合わない場合に発生します。  
  
 たとえば、開いていないファイルから読み出そうとしたり、既存の読み取り専用ファイルを書き込みモードで開こうとしたり、ファイルでなくディレクトリを開こうとしたりすると、このエラーが発生します。  MS\-DOS オペレーティング システムの Version 3.0 以降では、**EACCES** がロック違反または共有違反を示す場合があります。  
  
 また、ファイルまたはディレクトリを既存のディレクトリと同じ名前に変更しようとしたり、既存のディレクトリを削除しようとした場合にも、このエラーが発生します。  
  
 **EBADF**  
 不正なファイル番号。  次の 2 つの原因があります。1\) 指定されたファイル記述子が有効な値でないか、開いているファイルを参照していないとき。2\) 読み取り専用モードで開いているファイル、またはデバイスに書き込もうとしたとき。  
  
 **EDEADLOCK**  
 リソースのデットロックが発生する可能性がある。  数値演算関数の引数が、関数の定義域内にありません。  
  
 **EDOM**  
 数値演算関数の引数が関数のドメイン外の値である。  
  
 **EEXIST**  
 ファイルが存在する。  既に存在するファイルを作成しようとしています。  たとえば、**\_O\_CREAT** フラグおよび **\_O\_EXCL** フラグが **\_open** 呼び出しで指定されますが、指定した名前のファイルが既に存在している場合があります。  
  
 **EILSEQ**  
 無効なバイト シーケンス。たとえば、MBCS 文字列に含まれています。  
  
 **EINVAL**  
 不正な引数。  関数の引数のいずれかに無効な値が指定されています。  たとえば、**fseek** 呼び出しでファイル ポインターを移動するとき、指定した元の位置がファイルの先頭より前にある場合です。  
  
 **EMFILE**  
 開いているファイルが多すぎる。  使用できるファイル記述子が不足しているため、これ以上ファイルを開くことができません。  
  
 **ENOENT**  
 ファイルまたはディレクトリがない。  指定されたファイルまたはディレクトリが存在しないか、見つかりません。  このメッセージは、指定のファイルが存在しない場合、またはパスのコンポーネントが既存のディレクトリを指定していない場合に発生します。  
  
 **ENOEXEC**  
 実行ファイルのエラー。  実行可能形式でないか、無効な実行可能ファイル形式のファイルを実行しようとしました。  
  
 **ENOMEM**  
 メモリ不足。  メモリ不足のため、目的の操作を実行できません。  たとえば、このメッセージは、子プロセスを実行するためのメモリが不足している場合や、**\_getcwd** 呼び出しでの割り当て要求を満たすことができない場合に生成されます。  
  
 **ENOSPC**  
 デバイスの空き領域不足。  デバイスの書き込み可能領域が不足しています。たとえば、ディスクが満杯の場合です。  
  
 **ERANGE**  
 結果が大きすぎる。  数値演算関数の引数が大きすぎて、結果の有効数字の一部または全部が失われます。  このエラーは、引数が予想よりも大きい場合に他の関数でも発生することがあります。たとえば、**\_getcwd** の *buffer* 引数が予想より大きい場合です。  
  
 **EXDEV**  
 デバイス間リンク。  **rename** 関数を使用して、ファイルを別のデバイスに移動しようとしました。  
  
 **STRUNCATE**  
 結果として切り詰められる文字列のコピーまたは連結。  「[\_TRUNCATE](../c-runtime-library/truncate.md)」を参照してください。  
  
 Posix との互換性のために、次の値がサポートされています。  これらは、非 Posix システムで必要とされる値です。  
  
```  
#define E2BIG [argument list too long]  
#define EACCES [permission denied]  
#define EADDRINUSE [address in use]  
#define EADDRNOTAVAIL [address not available]  
#define EAFNOSUPPORT [address family not supported]  
#define EAGAIN [resource unavailable try again]  
#define EALREADY [connection already in progress]  
#define EBADF [bad file descriptor]  
#define EBADMSG [bad message]  
#define EBUSY [device or resource busy]  
#define ECANCELED [operation canceled]  
#define ECHILD [no child process]  
#define ECONNABORTED [connection aborted]  
#define ECONNREFUSED [connection refused]  
#define ECONNRESET [connection reset]  
#define EDEADLK [resource deadlock would occur]  
#define EDESTADDRREQ [destination address required]  
#define EDOM [argument out of domain]  
#define EEXIST [file exists]  
#define EFAULT [bad address]  
#define EFBIG [file too large]  
#define EHOSTUNREACH [host unreachable]  
#define EIDRM [identifier removed]  
#define EILSEQ [illegal byte sequence]  
#define EINPROGRESS [operation in progress]  
#define EINTR [interrupted]  
#define EINVAL [invalid argument]  
#define EIO [io error]  
#define EISCONN [already connected]  
#define EISDIR [is a directory]  
#define ELOOP [too many synbolic link levels]  
#define EMFILE [too many files open]  
#define EMLINK [too many links]  
#define EMSGSIZE [message size]  
#define ENAMETOOLONG [filename too long]  
#define ENETDOWN [network down]  
#define ENETRESET [network reset]  
#define ENETUNREACH [network unreachable]  
#define ENFILE [too many files open in system]  
#define ENOBUFS [no buffer space]  
#define ENODATA [no message available]  
#define ENODEV [no such device]  
#define ENOENT [no such file or directory]  
#define ENOEXEC [executable format error]  
#define ENOLCK [no lock available]  
#define ENOLINK [no link]  
#define ENOMEM [not enough memory]  
#define ENOMSG [no message]  
#define ENOPROTOOPT [no protocol option]  
#define ENOSPC [no space on device]  
#define ENOSR [no stream resources]  
#define ENOSTR [not a stream]  
#define ENOSYS [function not supported]  
#define ENOTCONN [not connected]  
#define ENOTDIR [not a directory]  
#define ENOTEMPTY [directory not empty]  
#define ENOTRECOVERABLE [state not recoverable]  
#define ENOTSOCK [not a socket]  
#define ENOTSUP [not supported]  
#define ENOTTY [inappropriate io control operation]  
#define ENXIO [no such device or address]  
#define EOPNOTSUPP [operation not supported]  
#define EOTHER [other]  
#define EOVERFLOW [value too large]  
#define EOWNERDEAD [owner dead]  
#define EPERM [operation not permitted]  
#define EPIPE [broken pipe]  
#define EPROTO [protocol error]  
#define EPROTONOSUPPORT [protocol not supported]  
#define EPROTOTYPE [wrong protocol type]  
#define ERANGE [result out of range]  
#define EROFS [read only file system]  
#define ESPIPE [invalid seek]  
#define ESRCH [no such process]  
#define ETIME [stream timeout]  
#define ETIMEDOUT [timed out]  
#define ETXTBSY [text file busy]  
#define EWOULDBLOCK [operation would block]  
#define EXDEV [cross device link]  
```  
  
## 参照  
 [グローバル定数](../c-runtime-library/global-constants.md)