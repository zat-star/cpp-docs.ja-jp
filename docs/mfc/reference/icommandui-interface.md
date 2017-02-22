---
title: "ICommandUI インターフェイス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ICommandUI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandUI インターフェイス"
ms.assetid: 134afe8d-dcdf-47ca-857a-a166a6b665dd
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# ICommandUI インターフェイス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユーザー インターフェイスのコマンドを管理します。  
  
## 構文  
  
```  
interface class ICommandUI  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[ICommandUI::Check](../Topic/ICommandUI::Check.md)|適切なチェック状態にこのコマンドのユーザー インターフェイス アイテムを設定します。|  
|[ICommandUI::ContinueRouting](../Topic/ICommandUI::ContinueRouting.md)|コマンド ルーティング機構をハンドラーのチェーンの下の現在のメッセージをルーティングするように指定します。|  
|[ICommandUI::Enabled](../Topic/ICommandUI::Enabled.md)|このコマンドのユーザー インターフェイス項目を有効または無効にします。|  
|[ICommandUI::ID](../Topic/ICommandUI::ID.md)|`ICommandUI` のオブジェクトによって表されるユーザー インターフェイス オブジェクトの ID を取得します。|  
|[ICommandUI::Index](../Topic/ICommandUI::Index.md)|`ICommandUI` のオブジェクトによって表されるユーザー インターフェイス オブジェクトのインデックスを取得します。|  
|[ICommandUI::Radio](../Topic/ICommandUI::Radio.md)|適切なチェック状態にこのコマンドのユーザー インターフェイス アイテムを設定します。|  
|[ICommandUI::Text](../Topic/ICommandUI::Text.md)|このコマンドのユーザー インターフェイス アイテムのテキストを設定します。|  
  
## 解説  
 このインターフェイスは、ユーザー インターフェイスのコマンドを管理するメソッドとプロパティを提供します。  `ICommandUI` は [CCmdUI クラス](../Topic/CCmdUI%20Class.md)に似ていますが、`ICommandUI` は、.NET コンポーネントと相互運用する MFC アプリケーションで使用されます。  
  
 `ICommandUI` は [ICommandTarget](../../mfc/reference/icommandtarget-interface.md)で `ON_UPDATE_COMMAND_UI` ハンドラーの派生クラスで使用されます。  アプリケーションのユーザーが、選択するか、をクリック\) メニューをアクティブにすると、各メニュー項目はが有効または無効にすると表示されます。  各メニュー コマンドの対象は `ON_UPDATE_COMMAND_UI` のハンドラーを実行してこの情報を提供します。  アプリケーションのコマンド ユーザー インターフェイス オブジェクトの場合、各ハンドラーに対するメッセージ マップ エントリと関数のプロトタイプを作成するには、プロパティ ウィンドウを使用します。  
  
 詳細については、`ICommandUI` のインターフェイスがコマンド ルーティングでの使用方法、[方法: Windows フォーム コントロールにコマンド ルーティングを追加する](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)を参照してください。  
  
 Windows フォームの使い方の詳細については、「[MFC での Windows フォーム ユーザー コントロールの使用](../../dotnet/using-a-windows-form-user-control-in-mfc.md)」を参照してください。  
  
 詳細については、ユーザー インターフェイスのコマンドが MFC でどのように管理されるか、[CCmdUI クラス](../Topic/CCmdUI%20Class.md)を参照してください。  
  
## 必要条件  
 **ヘッダー :** afxwinforms.h \(アセンブリ atlmfc\\lib\\mfcmifc80.dll で定義\)  
  
## 参照  
 [CCmdUI クラス](../Topic/CCmdUI%20Class.md)