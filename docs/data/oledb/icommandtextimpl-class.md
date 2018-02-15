---
title: "ICommandTextImpl クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandText
dev_langs:
- C++
helpviewer_keywords:
- ICommandText class
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 397f7b26d9f75813897309c99c40d5db94f06c53
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="icommandtextimpl-class"></a>ICommandTextImpl クラス
実装を提供、 [ICommandText](https://msdn.microsoft.com/en-us/library/ms714914.aspx)インターフェイスです。  
  
## <a name="syntax"></a>構文

```cpp
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