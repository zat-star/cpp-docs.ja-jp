---
title: "コンパイラ COM グローバル関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 28755b770594209d22de0ae6ac35323ebf61e109
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="compiler-com-global-functions"></a>コンパイラ COM のグローバル関数
**Microsoft 固有の仕様**  
  
 使用できるルーチンは次のとおりです。  
  
|関数|説明|  
|--------------|-----------------|  
|[_com_raise_error](../cpp/com-raise-error.md)|スロー、 [_com_error](../cpp/com-error-class.md)エラーに応答します。|  
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|COM のエラー処理に使用する既定の関数を置き換えます。|  
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|変換、`BSTR`値を**char \***です。|  
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|変換、 **char \* **値を`BSTR`です。|  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)   
 [コンパイラ COM サポート](../cpp/compiler-com-support.md)
