---
title: コンパイラ COM グローバル関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
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
ms.workload:
- cplusplus
ms.openlocfilehash: be73622037c1c058edffa681ccd79322b8252633
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-com-global-functions"></a>コンパイラ COM のグローバル関数
**Microsoft 固有の仕様**  
  
 使用できるルーチンは次のとおりです。  
  
|関数|説明|  
|--------------|-----------------|  
|[_com_raise_error](../cpp/com-raise-error.md)|スロー、 [_com_error](../cpp/com-error-class.md)エラーに応答します。|  
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|COM のエラー処理に使用する既定の関数を置き換えます。|  
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|変換、`BSTR`値を**char \***です。|  
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|変換、 **char \*** 値を`BSTR`です。|  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)   
 [コンパイラ COM サポート](../cpp/compiler-com-support.md)