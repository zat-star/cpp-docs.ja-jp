---
title: "コンパイラの警告 (レベル 1) C4581 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4581
dev_langs: C++
helpviewer_keywords: C4581
ms.assetid: 598bcd87-257d-4eb3-94e4-15bb31aadc99
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 59bf4eafe722283f5fced046e845c6b46ca3ce82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4581"></a>コンパイラの警告 (レベル 1) C4581
動作が使用されていません: '"string1"' が 'string2' 属性を処理に置き換えられます  
  
 このエラーは、Visual C 2005 で行ったコンパイラ準拠作業の結果として生成されることができます。 Visual c 属性のパラメーター チェックします。  
  
 以前のバージョンでは、属性値は引用符で囲まれているかどうかに受け入れられました。 値が列挙体の場合は、いない囲む必要があります引用符で囲んで指定します。  
  
## <a name="example"></a>例  
 次の例では、C4581 を生成します。  
  
```  
// C4581.cpp  
// compile with: /c /W1  
#include "unknwn.h"  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI : IUnknown {};  
  
[coclass, uuid(12345678-1111-2222-3333-123456789012), threading("free")]   // C4581  
// try the following line instead  
// [coclass, uuid(12345678-1111-2222-3333-123456789012), threading(free)]  
class CSample : public IMyI {};  
```