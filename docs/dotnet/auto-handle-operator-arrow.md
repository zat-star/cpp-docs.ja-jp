---
title: "auto_handle::operator-&gt; |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::auto_handle::operator->
- auto_handle.operator->
- auto_handle::operator->
- msclr.auto_handle.operator->
dev_langs:
- C++
helpviewer_keywords:
- auto_handle::operator->
ms.assetid: c8c7a771-ea15-41fa-981a-065b8d1162b4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7fcaef569626c21154437973c525aee85f4cd4cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="autohandleoperator-gt"></a>auto_handle::operator-&gt;
メンバー アクセス演算子です。  
  
## <a name="syntax"></a>構文  
  
```  
_element_type ^ operator->();  
```  
  
## <a name="return-value"></a>戻り値  
 オブジェクトによってラップされる`auto_handle`です。  
  
## <a name="example"></a>例  
  
```  
// msl_auto_handle_op_arrow.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:     
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {}  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
  
   int m_i;  
};  
  
int main() {  
   auto_handle<ClassA> a( gcnew ClassA( "first" ) );  
   a->PrintHello();  
  
   a->m_i = 5;  
   Console::WriteLine( "a->m_i = {0}", a->m_i );  
}  
```  
  
```Output  
Hello from first A!  
a->m_i = 5  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー ファイル** \<msclr\auto_handle.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>参照  
 [auto_handle メンバー](../dotnet/auto-handle-members.md)   
 [auto_handle::get](../dotnet/auto-handle-get.md)