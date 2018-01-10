---
title: "リンカー ツールの警告 LNK4227 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4227
dev_langs: C++
helpviewer_keywords: LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c603110d77b06fac59a725ba448f058bd4ad7a38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4227"></a>リンカー ツールの警告 LNK4227  
  
> メタデータ操作の警告 (*HRESULT*): *warning_message*  
  
リンカーでは、マージするときに、メタデータの違いが検出されました。  
  
-   現在作成されているアセンブリでの 1 つ以上の参照先のアセンブリ。  
  
-   1 つまたは複数ソース コード ファイルとしてコンパイルします。  
  
たとえば、LNK4227 が考えられますで同じ名前が異なる方法で宣言されているパラメーターについて 2 つのグローバル関数がある場合 (つまり、宣言で一貫していないすべてのコンパイル単位)。 Ildasm.exe/TEXT を使用して/METADATA *object_file*型の動作の違いを表示するには、各 .obj ファイルにします。  
  
LNK4227 は、別のツールで発生した問題の報告も使用されます。 詳細については、警告メッセージを検索します。  
  
警告を解決するには、メタデータの問題を修正してください。  
  
## <a name="example"></a>例  
  
参照アセンブリが参照するアセンブリとは異なる署名されている場合、LNK4227 が生成されます。  
  
次の例では、LNK4227 が生成されます。  
  
```cpp  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 それから  
  
```cpp  
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
  
## <a name="example"></a>例  
  
LNK4227 は、形式が正しくないバージョン番号は、アセンブリの属性に渡されるときにも生成できます。  ' *' に固有の表記法、`AssemblyVersionAttribute`です。  この警告を解決するには、使用のみに番号バージョン属性以外の`AssemblyVersionAttribute`します。  
  
次の例では、LNK4227 が生成されます。  
  
```cpp  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```