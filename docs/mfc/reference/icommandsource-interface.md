---
title: "ICommandSource インターフェイス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ICommandSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandSource インターフェイス"
ms.assetid: a4b1f698-c09f-4ba8-9b13-0e74a0a4967e
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# ICommandSource インターフェイス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コマンド ソースから送信された管理コマンドはユーザー コントロールに追加します。  
  
## 構文  
  
```  
interface class ICommandSource  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[ICommandSource::AddCommandHandler](../Topic/ICommandSource::AddCommandHandler.md)|コマンド ハンドラーをコマンド ソース オブジェクトに追加します。|  
|[ICommandSource::AddCommandRangeHandler](../Topic/ICommandSource::AddCommandRangeHandler.md)|コマンド ソース オブジェクトにコマンド ハンドラーのグループを追加します。|  
|[ICommandSource::AddCommandRangeUIHandler](../Topic/ICommandSource::AddCommandRangeUIHandler.md)|コマンド ソース オブジェクトにユーザー インターフェイスのコマンド メッセージのハンドラーのグループを追加します。|  
|[ICommandSource::AddCommandUIHandler](../Topic/ICommandSource::AddCommandUIHandler.md)|コマンド ソース オブジェクトにユーザー インターフェイスのコマンド メッセージのハンドラーを追加します。|  
|[ICommandSource::PostCommand](../Topic/ICommandSource::PostCommand.md)|処理されるまで待たずにメッセージをポストします。|  
|[ICommandSource::RemoveCommandHandler](../Topic/ICommandSource::RemoveCommandHandler.md)|コマンド ソース オブジェクトからコマンド ハンドラーを削除します。|  
|[ICommandSource::RemoveCommandRangeHandler](../Topic/ICommandSource::RemoveCommandRangeHandler.md)|コマンド ソース オブジェクトからコマンド ハンドラーのグループを削除します。|  
|[ICommandSource::RemoveCommandRangeUIHandler](../Topic/ICommandSource::RemoveCommandRangeUIHandler.md)|コマンド ソース オブジェクトからユーザー インターフェイスのコマンド メッセージのハンドラーのグループを削除します。|  
|[ICommandSource::RemoveCommandUIHandler](../Topic/ICommandSource::RemoveCommandUIHandler.md)|コマンド ソース オブジェクトからユーザー インターフェイスのコマンド メッセージのハンドラーを削除します。|  
|[ICommandSource::SendCommand](../Topic/ICommandSource::SendCommand.md)|メッセージの送信、返される前に処理されるまで待機します。|  
  
## 解説  
 MFC ビュー ユーザー コントロールをホストすると MFC コマンドを処理するように、[CWinFormsView クラス](../../mfc/reference/cwinformsview-class.md) は、ユーザー コントロールにコマンド、更新コマンドの UI メッセージをルーティングします \(たとえば、フレーム メニュー項目とツール バー ボタン\)。  [ICommandTarget インターフェイス](../../mfc/reference/icommandtarget-interface.md)の実装によって、ユーザー コントロールに `ICommandSource` のオブジェクトへの参照を追加します。  
  
 `ICommandTarget` の使用例については、「[方法: Windows フォーム コントロールにコマンド ルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)」を参照してください。  
  
 Windows フォームの使い方の詳細については、「[MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。  
  
## 必要条件  
 **ヘッダー :** afxwinforms.h \(アセンブリ atlmfc\\lib\\mfcmifc80.dll で定義\)  
  
## 参照  
 [方法: Windows フォーム コントロールにコマンド ルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [ICommandTarget インターフェイス](../../mfc/reference/icommandtarget-interface.md)