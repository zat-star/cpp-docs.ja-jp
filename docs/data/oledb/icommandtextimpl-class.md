---
title: "ICommandTextImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ICommandText
dev_langs: C++
helpviewer_keywords: ICommandText class
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 53b5e19fbeaccfb61380054426315ad9b92f624a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl クラス
実装を提供、 [ICommandText](https://msdn.microsoft.com/en-us/library/ms714914.aspx)インターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```  
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 コマンド クラスから派生する**ICommandTextImpl**です。  
  
## <a name="members"></a>メンバー  
  
### <a name="interface-methods"></a>インターフェイス メソッド  
  
|||  
|-|-|  
|[GetCommandText](../../data/oledb/icommandtextimpl-getcommandtext.md)|テキスト コマンドの最後の呼び出しでセットを返します[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)です。|  
|[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)|コマンド テキストは、既存のコマンド テキストの置換を設定します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[m_strCommandText](../../data/oledb/icommandtextimpl-m-strcommandtext.md)|コマンド テキストを格納します。|  
  
## <a name="remarks"></a>コメント  
 コマンドの必須のインターフェイスです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** altdb.h  
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)