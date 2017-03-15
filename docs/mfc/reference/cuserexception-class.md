---
title: "チェック クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserException
dev_langs:
- C++
helpviewer_keywords:
- operations [C++], stopping
- exceptions, throwing
- CUserException class
- errors [C++], trapping
- operations [C++]
- throwing exceptions, stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
caps.latest.revision: 23
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 8548ffa7ad9032e174d650e210a70a29b0e3f19d
ms.lasthandoff: 02/24/2017

---
# <a name="cuserexception-class"></a>チェック クラス
エンド ユーザーの操作を中止するためにスローします。  
  
## <a name="syntax"></a>構文  
  
```  
class CUserException : public CSimpleException  
```  
  
## <a name="remarks"></a>コメント  
 使用して`CUserException`アプリケーション固有の例外のスローと catch 例外処理機構を使用する場合。 クラス名の"user"は「アプリケーションのユーザーが例外を処理することが必要です」と解釈できます。  
  
 A`CUserException`は通常、グローバル関数を呼び出した後にスローされます`AfxMessageBox`操作に失敗しましたが、ユーザーに通知します。 例外ハンドラーを記述する場合は、ユーザー通常に既に通知されました、エラーのために特別に例外を処理します。 フレームワークは、場合によっては、この例外をスローします。 スローする、`CUserException`ユーザーに通知して、グローバル関数を呼び出し、自分で`AfxThrowUserException`します。  
  
 次の例で操作が失敗するを含む関数をユーザーに通知し、スロー、`CUserException`です。 呼び出し元の関数は、例外をキャッチし、専用の処理します。  
  
 [!code-cpp[NVC_MFCExceptions #&24;](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]  
  
 使用する方法について`CUserException`、記事を参照して[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CUserException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxwin.h  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)

