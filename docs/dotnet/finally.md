---
title: 最後に |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- finally keyword [C++]
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dd357c8eeed9eddc6940ce02de6e5d2b4f8c68d0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="finally"></a>finally
加え`try`と`catch`句、CLR の例外処理のサポート、`finally`句。 セマンティクスは次のと同じ、`__finally`構造化例外処理 (SEH) をブロックします。 A`__finally`ブロックに従って、`try`または`catch`ブロックします。  
  
## <a name="remarks"></a>コメント  
 目的、`finally`例外が発生した後に残されているリソースをクリーンアップするのには、ブロックします。 なお、`finally`ブロックは常に実行、例外がスローされなかった場合でもです。 `catch`マネージ例外がスローされた場合、ブロックは実行のみが関連付けられている`try`ブロックします。  
  
 `finally`状況依存のキーワードです。参照してください[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では、単純な`finally`ブロック。  
  
```  
// keyword__finally.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyException: public System::Exception{};  
  
void ThrowMyException() {  
   throw gcnew MyException;  
}  
  
int main() {  
   try {  
      ThrowMyException();  
   }  
   catch ( MyException^ e ) {  
      Console::WriteLine(  "in catch" );  
      Console::WriteLine( e->GetType() );  
   }  
   finally {  
      Console::WriteLine(  "in finally" );  
   }  
}  
```  
  
```Output  
in catch  
MyException  
in finally  
```  
  
## <a name="see-also"></a>参照  
 [例外処理](../windows/exception-handling-cpp-component-extensions.md)