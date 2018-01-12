---
title: "方法: clr コンパイルでネイティブ型を使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- compilation, native types in /clr
- /clr compiler option [C++], using native types
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c0a73d5bd9c165645dbf3c3cdee7a740cc3c16a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-a-native-type-in-a-clr-compilation"></a>方法: /clr コンパイルでネイティブ型を使用する
ネイティブ型を定義することができます、 **/clr**コンパイルと、アセンブリ内からそのネイティブ型を使用するが無効です。 ただし、ネイティブ型は参照されたメタデータから使用できません。  
  
 各アセンブリは、使用するすべてのネイティブ型の定義を含める必要があります。  
  
 詳細については、「[/clr (共通言語ランタイムのコンパイル)](../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
## <a name="example"></a>例  
 このサンプルを定義し、ネイティブ型を使用するコンポーネントを作成します。  
  
```  
// use_native_type_in_clr.cpp  
// compile with: /clr /LD  
public struct NativeClass {  
   static int Test() { return 98; }  
};  
  
public ref struct ManagedClass {  
   static int i = NativeClass::Test();  
   void Test() {  
      System::Console::WriteLine(i);  
   }  
};  
```  
  
## <a name="example"></a>例  
 このサンプルでは、コンポーネントを使用するクライアントを定義します。 コンパイル単位で定義されている場合を除き、ネイティブ型にアクセスすると、エラーであることに注意してください。  
  
```  
// use_native_type_in_clr_2.cpp  
// compile with: /clr  
#using "use_native_type_in_clr.dll"  
// Uncomment the following 3 lines to resolve.  
// public struct NativeClass {  
//    static int Test() { return 98; }  
// };  
  
int main() {  
   ManagedClass x;  
   x.Test();  
  
   System::Console::WriteLine(NativeClass::Test());   // C2653  
}  
```  
  
## <a name="see-also"></a>参照  
 [C++ Interop (暗黙の PInvoke) の使用](../dotnet/using-cpp-interop-implicit-pinvoke.md)