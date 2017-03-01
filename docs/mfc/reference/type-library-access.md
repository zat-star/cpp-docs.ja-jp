---
title: "ライブラリへのアクセスを入力 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- type libraries, accessing
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 14
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8a3fbcf66036ef3df3bd34b5182dac8af3dfccef
ms.lasthandoff: 02/24/2017

---
# <a name="type-library-access"></a>タイプ ライブラリ アクセス
タイプ ライブラリでは、他の OLE 対応のアプリケーションに対する OLE コントロールのインターフェイスを公開します。 各 OLE コントロールは、1 つまたは複数のインターフェイスを公開する場合、タイプ ライブラリにすることが必要です。  
  
 次のマクロは、タイプ ライブラリへのアクセスを提供する OLE コントロールを使用します。  
  
### <a name="type-library-access"></a>タイプ ライブラリ アクセス  
  
|||  
|-|-|  
|[DECLARE_OLETYPELIB](#declare_oletypelib)|宣言、 `GetTypeLib` (クラス宣言で使用する必要があります) OLE コントロールのメンバー関数。|  
|[IMPLEMENT_OLETYPELIB](#implement_oletypelib)|実装して、 `GetTypeLib` (クラスの実装で使用する必要があります) OLE コントロールのメンバー関数。|  
  
##  <a name="a-namedeclareoletypeliba--declareoletypelib"></a><a name="declare_oletypelib"></a>DECLARE_OLETYPELIB  
 宣言、`GetTypeLib`コントロール クラスのメンバー関数。  
  
```   
DECLARE_OLETYPELIB(class_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 タイプ ライブラリに関連するコントロール クラスの名前。  
  
### <a name="remarks"></a>コメント  
 コントロール クラスのヘッダー ファイルでこのマクロを使用します。  

### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  

##  <a name="a-nameimplementoletypeliba--implementoletypelib"></a><a name="implement_oletypelib"></a>IMPLEMENT_OLETYPELIB  
 コントロールの実装`GetTypeLib`メンバー関数。  
  
```   
IMPLEMENT_OLETYPELIB(class_name, tlid, wVerMajor,  wVerMinor)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 タイプ ライブラリに関連するコントロール クラスの名前。  
  
 *tlid*  
 タイプ ライブラリの ID 番号。  
  
 `wVerMajor`  
 タイプ ライブラリのメジャー バージョン番号。  
  
 `wVerMinor`  
 タイプ ライブラリのマイナー バージョン番号。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用するコントロール クラスの実装ファイルに表示する必要があります、`DECLARE_OLETYPELIB`マクロです。  

### <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
   
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

