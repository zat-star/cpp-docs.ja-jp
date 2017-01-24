---
title: "ICommandTextImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandText"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandText クラス"
ms.assetid: 9c2715cc-1e55-4468-8327-85341617ed46
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ICommandTextImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[ICommandText](https://msdn.microsoft.com/en-us/library/ms714914.aspx) インターフェイスの実装を提供します。  
  
## 構文  
  
```  
template <class T >  
class ATL_NO_VTABLE ICommandTextImpl   
   : public ICommandImpl<T, ICommandText>  
```  
  
#### パラメーター  
 `T`  
 **ICommandTextImpl**から派生したクラスで、コマンド。  
  
## メンバー  
  
### インターフェイス メソッド  
  
|||  
|-|-|  
|[GetCommandText](../../data/oledb/icommandtextimpl-getcommandtext.md)|最後のオーダーによって設定された [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)にテキスト コマンドを返します。|  
|[SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md)|既存のコマンド テキストを置換コマンド テキストを設定します。|  
  
### データ メンバー  
  
|||  
|-|-|  
|[m\_strCommandText](../../data/oledb/icommandtextimpl-m-strcommandtext.md)|コマンド テキストを格納します。|  
  
## 解説  
 コマンドの必須インターフェイス。  
  
## 必要条件  
 **ヘッダー:** altdb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)