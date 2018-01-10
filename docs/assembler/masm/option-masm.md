---
title: "オプション (MASM) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: option
dev_langs: C++
helpviewer_keywords: OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f449606b143bfbf188e878b261f3d35017846862
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="option-masm"></a>OPTION (MASM)
有効にして、アセンブラーの機能を無効になります。  
  
## <a name="syntax"></a>構文  
  
```  
  
OPTION   
optionlist  
  
```  
  
## <a name="remarks"></a>コメント  
 使用可能なオプションは次のとおりです。  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**エミュレーター**|  
|**NOEMULATOR**|**エピローグ**|**EXPR16**|**EXPR32**|  
|**言語**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**オフセット**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**プロローグ**|**読み取り専用**|**NOREADONLY**|  
|**スコープ**|**NOSCOPED**|**SEGMENT**|**SETIF2**です。|  
  
 言語の構文は、**オプション言語:***x*ここで、 *x* C、SYSCALL、STDCALL、PASCAL、FORTRAN、または BASIC の 1 つです。  SYSCALL、PASCAL、FORTRAN、および BASIC ではサポートされません併用[です。モデル](../../assembler/masm/dot-model.md)フラットです。  
  
## <a name="see-also"></a>参照  
 [ディレクティブ リファレンス](../../assembler/masm/directives-reference.md)