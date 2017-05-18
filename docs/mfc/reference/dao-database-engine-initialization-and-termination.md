---
title: "DAO データベース エンジンの初期化と終了 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.data
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), termination
- DAO (Data Access Objects), initialization
ms.assetid: a7edf31c-e7c2-4f3e-aada-63c3e48781da
caps.latest.revision: 13
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b6119279234558998fad1f220239a29618c69cc5
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="dao-database-engine-initialization-and-termination"></a>DAO データベース エンジンの初期化と終了
DAO データベース エンジンが最初にする必要があります MFC DAO オブジェクトを使用するときに初期化され、終了、アプリケーションまたは DLL が終了する前にします。 2 つの関数`AfxDaoInit`と`AfxDaoTerm`、これらのタスクを実行します。  
  
### <a name="dao-database-engine-initialization-and-termination"></a>DAO データベース エンジンの初期化と終了  
  
|||  
|-|-|  
|[AfxDaoInit](#afxdaoinit)|DAO データベース エンジンを初期化します。|  
|[AfxDaoTerm](#afxdaoterm)|データベース エンジンの初期化を終了します。|  
  
##  <a name="afxdaoinit"></a>AfxDaoInit  
 この関数は、DAO データベース エンジンを初期化します。  
  
```  
 
void AfxDaoInit();

throw(CDaoException*);  
```  
  
### <a name="remarks"></a>コメント  
 ほとんどの場合を呼び出す必要はありません`AfxDaoInit`は必要に応じて、アプリケーションが自動的に呼び出すためです。  
  
 呼び出しの例については、関連情報については、`AfxDaoInit`を参照してください[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  
  
##  <a name="afxdaoterm"></a>AfxDaoTerm  
 この関数は、データベース エンジンの初期化を終了します。  
  
```  
 
void AfxDaoTerm();  
```  
  
### <a name="remarks"></a>コメント  
 通常、だけで済みます。 レギュラー DLL でこの関数を呼び出すアプリケーションが自動的に呼び出さ`AfxDaoTerm`が必要です。  
  
 レギュラー Dll で呼び出す`AfxDaoTerm`する前に、`ExitInstance`関数の場合、すべての MFC DAO オブジェクトが破棄された後です。  
  
 関連情報については、次を参照してください。[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)します。  

### <a name="requirements"></a>要件  
  **ヘッダー** afxdao.h  

## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

