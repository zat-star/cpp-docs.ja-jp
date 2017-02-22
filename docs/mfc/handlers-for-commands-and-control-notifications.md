---
title: "コマンドとコントロール通知のハンドラー | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コマンド, ハンドラー"
  - "コントロール [MFC], 通知"
  - "関数 [C++], ハンドラー"
  - "ハンドラー"
  - "ハンドラー, コマンド"
  - "ハンドラー, コントロール通知"
  - "通知, ハンドラー (コントロールの)"
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# コマンドとコントロール通知のハンドラー
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

コマンドまたはコントロール通知メッセージの既定のハンドラーはありません。  したがって、メッセージのこれらのカテゴリのハンドラーに名前を付けることで規則でのみバインドされます。  ハンドラーにコマンドやコントロール通知をマップするときに、プロパティ ウィンドウにコマンド ID またはコントロール通知コードに基づいて名前を示します。  指定された名前を受け入れるか、変更、または置換できます。  
  
 規則を表すユーザー インターフェイス オブジェクトの両方のカテゴリのハンドラーの名前を付けることをお勧めします。  したがって、編集メニューの切り取りのハンドラーは名前の場合があります。  
  
 [!CODE [NVC_MFCMessageHandling#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#4)]  
  
 切り取りコマンドがアプリケーションに、一般に実装されるので、フレームワークは **ID\_EDIT\_CUT**として切り取りコマンドのコマンド ID を定義します。  すべての定義済みのなコマンド ID の一覧については、ファイル AFXRES.H.を参照してください。  詳細については、「[標準のコマンド](../mfc/standard-commands.md)」を参照してください。  
  
 また、規則は「\<cf style\= " Button」というラベルのボタンの **BN\_CLICKED** 通知メッセージ ハンドラーが名前の可能性があることを示します。  
  
 [!CODE [NVC_MFCMessageHandling#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#5)]  
  
 アプリケーション固有のユーザー インターフェイス オブジェクトと同じであるため、このコマンドに `IDC_MY_BUTTON` の ID を割り当てる場合があります。  
  
 メッセージのカテゴリは、引数を受け取らず、値を返しません。  
  
## 参照  
 [メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)