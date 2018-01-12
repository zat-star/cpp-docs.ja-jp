---
title: "バッチモード規則 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0faeb66f728c826f8d499ee6f033cecc7250a5b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="batch-mode-rules"></a>バッチモード規則
```  
{frompath}.fromext{topath}.toext::  
   commands  
```  
  
 バッチモード推論規則は、n 個のコマンドがその推論規則を通過するときに、推論規則の 1 つだけの呼び出しを提供します。 バッチモード推論のルールを伴わない呼び出される n 個のコマンドが必要になります。 N は、推論規則をトリガーする依存オブジェクトの数です。  
  
 バッチモード推論規則が含まれているメイクファイルでは、NMAKE 1.62 以降のバージョンを使用する必要があります。 (Nmake の) バージョンを確認するには、1.62 以降 (nmake の) バージョンで利用可能な _NMAKE_VER マクロを実行します。 このマクロは、Visual C 製品バージョンを表す文字列を返します。  
  
 標準の推論規則と構文のみの違いは、バッチモード推論規則が二重のコロン (:) で終了したことです。  
  
> [!NOTE]
>  呼び出されているツールは、複数のファイルを処理できる必要があります。 バッチモード推論規則を使用する必要があります`$<`依存ファイルにアクセスするマクロとして。  
  
 バッチモード推論規則は、ビルド処理を高速化できます。 これは高速のバッチにおいて、コンパイラにファイルを指定するコンパイラ ドライバーが 1 回だけ呼び出されるためです。 たとえば、C および C++ コンパイラ優れてプロセス中に常駐しているメモリを保持できる一連のファイルを処理するときにします。  
  
 次の例では、バッチ モードの推論規則を使用する方法を示します。  
  
```  
#  
# sample makefile to illustrate batch-mode inference rules  
#  
O = .  
S = .  
Objs = $O/foo1.obj $O/foo2.obj $O/foo2.obj $O/foo3.obj $O/foo4.obj  
CFLAGS = -nologo  
  
all : $(Objs)  
  
!ifdef NOBatch  
{$S}.cpp{$O}.obj:  
!else  
{$S}.cpp{$O}.obj::  
!endif  
   $(CC) $(CFLAGS) -Fd$O\ -c $<  
  
$(Objs) :  
  
#end of makefile  
```  
  
 (Nmake の) には、バッチ モードの推論規則のない次の出力が生成されます。  
  
```  
E:\tmp> nmake -f test.mak -a NOBatch=1  
  
Microsoft (R) Program Maintenance Utility   Version 7.00.0000  
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.  
        cl -nologo -Fd.\ -c .\foo1.cpp  
foo1.cpp  
        cl -nologo -Fd.\ -c .\foo2.cpp  
foo2.cpp  
        cl -nologo -Fd.\ -c .\foo3.cpp  
foo3.cpp  
        cl -nologo -Fd.\ -c .\foo4.cpp  
foo4.cpp  
```  
  
 Nmake の推論の規則をバッチ モードでは、次の結果。  
  
```  
E:\tmp> nmake -f test.mak -a  
  
Microsoft (R) Program Maintenance Utility   Version 7.00.0000  
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.  
  
        cl -nologo -Fd.\ -c .\foo1.cpp .\foo2.cpp .\foo3.cpp .\foo4.cpp  
foo1.cpp  
foo2.cpp  
foo3.cpp  
foo4.cpp  
Generating Code...  
```  
  
## <a name="see-also"></a>参照  
 [推論規則](../build/inference-rules.md)