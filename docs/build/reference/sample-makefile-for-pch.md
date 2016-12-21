---
title: "PCH のサンプル メイクファイル | Microsoft Docs"
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
  - "pch"
dev_langs: 
  - "C++"
ms.assetid: daf68983-77dc-45db-8701-aa89ad18910d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# PCH のサンプル メイクファイル
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次のメイクファイルは、マクロと \!IF, \!ELSE, \!ENDIF フロー制御コマンド構造を使用して、実際のプロジェクトに簡単に応用できるようにしています。  
  
```  
# Makefile : Illustrates the effective use of precompiled  
#            headers in a project  
# Usage:     NMAKE option  
# option:    DEBUG=[0|1]  
#            (DEBUG not defined is equivalent to DEBUG=0)  
#  
OBJS = myapp.obj applib.obj  
# List all stable header files in the STABLEHDRS macro.  
STABLEHDRS = stable.h another.h  
# List the final header file to be precompiled here:  
BOUNDRY = stable.h  
# List header files under development here:  
UNSTABLEHDRS = unstable.h  
# List all compiler options common to both debug and final  
# versions of your code here:  
CLFLAGS = /c /W3  
# List all linker options common to both debug and final  
# versions of your code here:  
LINKFLAGS = /NOD /ONERROR:NOEXE  
!IF "$(DEBUG)" == "1"  
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi /f  
LINKFLAGS = $(LINKFLAGS) /COD  
LIBS      = slibce  
!ELSE  
CLFLAGS   = $(CLFLAGS) /Oselg /Gs  
LINKFLAGS = $(LINKFLAGS)  
LIBS      = slibce  
!ENDIF  
myapp.exe: $(OBJS)  
    link $(LINKFLAGS) @<<  
$(OBJS), myapp, NUL, $(LIBS), NUL;  
<<  
# Compile myapp  
myapp.obj  : myapp.cpp $(UNSTABLEHDRS)  stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    myapp.cpp  
# Compile applib  
applib.obj : applib.cpp $(UNSTABLEHDRS) stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    applib.cpp  
# Compile headers  
stable.pch : $(STABLEHDRS)  
    $(CPP) $(CLFLAGS) /Yc$(BOUNDRY)    applib.cpp myapp.cpp  
```  
  
 このメイクファイルでは、「[ビルド プロセスでの PCH ファイル](../Topic/PCH%20Files%20in%20the%20Build%20Process.md)」の図「プリコンパイル済みヘッダー ファイルを使用するメイクファイルの構造」で示されている STABLEHDRS、BOUNDRY、および UNSTABLEHDRS の各マクロのほかに、CLFLAGS マクロと LINKFLAGS マクロが使用されています。  これらのマクロを使用して、適用するコンパイラ オプションとリンカー オプションを指定する必要があります。これは、ビルドするアプリケーションの実行可能ファイルがデバッグ バージョンであるか、最終バージョンであるかには関係ありません。  また、LIBS マクロも使用されています。このマクロには、プロジェクトに必要なライブラリを指定します。  
  
 また、このメイクファイルでは \!IF、\!ELSE、\!ENDIF を使用して、NMAKE コマンド ラインに DEBUG シンボルを定義するかどうかを判定しています。  
  
```  
NMAKE DEBUG=[1|0]  
```  
  
 この機能により、開発中のプログラムと最終バージョンのプログラムに同じメイクファイルを使用できます。最終バージョンには、DEBUG\=0 を使用します。  次の 2 つのコマンド ラインは、等価です。  
  
```  
NMAKE   
NMAKE DEBUG=0  
```  
  
 メイクファイルの詳細については、「[NMAKE リファレンス](../../build/nmake-reference.md)」を参照してください。  また、「[コンパイラ オプション](../../build/reference/compiler-options.md)」と「[リンカー オプション](../../build/reference/linker-options.md)」も参照してください。  
  
## 参照  
 [プロジェクトでのプリコンパイル済みヘッダーの使用](../../build/reference/using-precompiled-headers-in-a-project.md)