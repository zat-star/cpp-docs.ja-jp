---
title: "リンカー ツールの警告 LNK4227 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4227
dev_langs:
- C++
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ee566318c7d19159f9a2c084d348b5010a65e2de
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4227"></a>リンカー ツールの警告 LNK4227
メタデータ操作の警告 (HRESULT): warning_message  
  
リンカーでは、マージするときに、メタデータの違いが検出されました。  
  
-   現在構築中のアセンブリと参照先アセンブリを&1; つまたは複数。  
  
-   1 つまたは複数ソース コード ファイルにコンパイルします。  
  
たとえば、LNK4227 は起こります&2; つのグローバル関数で、同じ名前が異なる方法で宣言されたパラメーター情報がある場合 (宣言はすべてのコンパイル単位で一貫していない)。 Ildasm.exe/TEXT を使用して/METADATA`object_file`に各 .obj ファイルが表示されます、型の違いです。  
  
LNK4227 はまた別のツールで発生した問題を報告します。 たとえば、al.exe です。参照してください[Al.exe ツールのエラーと警告](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)します。  
  
警告を解決するのには、メタデータの問題を修正してください。  
  
たとえば、参照先アセンブリが参照するアセンブリとは異なる署名されたときに、LNK4227 が生成されます。  
  
次の例では、LNK4227 が生成されます。  
  
```  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 それから  
  
```  
// LNK4227b.cpp  
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
// Try the following line instead  
// [assembly:AssemblyDelaySignAttribute(false)];  
  
ref class MyClass  
{  
};  
```  
  
LNK4227 は、アセンブリ属性に正しくない形式のバージョン番号が渡されるときにも生成されることができます。  ' *' 表記は、しますに固有です。  この警告を解決するのには、します以外のバージョン属性の数値のみを使用します。  
  
次の例では、LNK4227 が生成されます。  
  
```  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```
