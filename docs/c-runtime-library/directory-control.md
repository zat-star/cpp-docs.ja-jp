---
title: "ディレクトリ制御 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.programs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "コントロール [C++], ディレクトリ"
  - "ディレクトリ制御ルーチン"
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ディレクトリ制御
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ディレクトリ制御ルーチンは、ディレクトリ構造に関する情報に対するアクセス、変更、および取得を行うときに使用します。  
  
### ディレクトリ制御ルーチン  
  
|ルーチン|使用方法|同等の .NET Framework 関数|  
|----------|----------|---------------------------|  
|[\_chdir、\_wchdir](../Topic/_chdir,%20_wchdir.md)|現在の作業ディレクトリを変更します。|[\<caps:sentence id\="tgt8" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_chdrive](../c-runtime-library/reference/chdrive.md)|現在のドライブを変更します。|[\<caps:sentence id\="tgt11" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getcwd、\_wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|既定のドライブについて現在の作業ディレクトリを取得します。|[\<caps:sentence id\="tgt14" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdcwd、\_wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|指定されたドライブについて現在の作業ディレクトリを取得します。|[\<caps:sentence id\="tgt16" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdiskfree](../Topic/_getdiskfree.md)|ディスク ドライブに関する情報を `_diskfree_t` 構造体に設定します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_getdrive](../c-runtime-library/reference/getdrive.md)|現在の \(既定の\) ドライブを取得します。|[\<caps:sentence id\="tgt23" sentenceid\="6aacc5c9471c794e236850e17f3f1787" class\="tgtSentence"\>System::Environment::CurrentDirectory\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)|  
|[\_getdrives](../Topic/_getdrives.md)|現在使用できるディスク ドライブを表すビットマスクを返します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
|[\_mkdir、\_wmkdir](../Topic/_mkdir,%20_wmkdir.md)|新しいディレクトリを作成します。|[System::IO::Directory::CreateDirectory](https://msdn.microsoft.com/en-us/library/system.io.directory.createdirectory.aspx)、[System::IO::DirectoryInfo::CreateSubdirectory](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.createsubdirectory.aspx)|  
|[\_rmdir、\_wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|ディレクトリを削除します。|[\<caps:sentence id\="tgt32" sentenceid\="de5c5e84e86fdd3cd99296d3b2518f57" class\="tgtSentence"\>System::IO::Directory::Delete\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.directory.delete.aspx)|  
|[\_searchenv、\_wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [\_searchenv\_s、\_wsearchenv\_s](../Topic/_searchenv_s,%20_wsearchenv_s.md)|指定されたパスで特定のファイルを検索します。|使用できません。  標準 C 関数を呼び出すには、`PInvoke` を使用します。  詳細については、「[プラットフォーム呼び出しの例](../Topic/Platform%20Invoke%20Examples.md)」を参照してください。|  
  
## 参照  
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)   
 [ファイル処理](../c-runtime-library/file-handling.md)   
 [システム コール](../Topic/System%20Calls.md)