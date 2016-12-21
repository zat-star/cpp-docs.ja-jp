---
title: "日時指定コントロールでのコールバック フィールドの使い方 | Microsoft Docs"
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
  - "DTN_FORMATQUERY"
  - "DTN_FORMAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コールバック フィールド (CDateTimeCtrl クラスの)"
  - "CDateTimeCtrl クラス, コールバック フィールド"
  - "CDateTimeCtrl クラス, 処理 (DTN_FORMAT と DTN_FORMATQ を)"
  - "DateTimePicker コントロール [MFC]"
  - "DateTimePicker コントロール [MFC], コールバック フィールド"
  - "DTN_FORMAT 通知"
  - "DTN_FORMATQUERY 通知"
ms.assetid: 404f4ba9-cba7-4718-9faa-bc6b274a723f
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 日時指定コントロールでのコールバック フィールドの使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

日時指定フィールドを定義する標準書式文字に加え、コールバック フィールドとしてカスタム書式指定文字列の一部を指定すると、出力をカスタマイズできます。  コールバック フィールドを宣言するには、書式指定文字列の本体に一つ以上「X」文字 \(ASCII コード 88\) の任意の場所を指定します。  たとえば、次の文字列が「今日「次の操作: 「yy」と"または「MM」または「dd」日 \(X\) 「日時指定のコントロール、年、月の日付、finally の日に続く"として現在の値を表示します。  
  
> [!NOTE]
>  コールバック フィールドの残りのカウントが表示された文字数に対応しません。  
  
 カスタム文字列に対してコールバック フィールドの間に「X」文字の繰り返しで区別できます。  したがって、書式指定文字列 XXddddMMMdd 「、「は yyyXXX」2 "の一意のコールバック フィールド「xx」および「XXX」が含まれています。  
  
> [!NOTE]
>  コールバック フィールドは、有効なフィールドとして扱われます。したがって、**DTN\_WMKEYDOWN** の通知メッセージを処理するようにする必要があります。  
  
 日時指定のコントロールのコールバック フィールドを実装すると、3 人の部分から成ります。:  
  
-   カスタム書式指定文字列の初期化  
  
-   **DTN\_FORMATQUERY** 通知の処理  
  
-   **DTN\_FORMAT** 通知の処理  
  
## カスタム書式指定文字列の初期化  
 `CDateTimeCtrl::SetFormat`を呼び出してカスタム文字列を初期化してください。  詳細については、「[日時指定のコントロールのカスタム書式指定文字列を使用します。](../mfc/using-custom-format-strings-in-a-date-and-time-picker-control.md)」を参照してください。  カスタム書式指定文字列を設定する共通の場所を含むビュー クラスの `OnInitialUpdate` を含むダイアログ クラスの `OnInitDialog` 関数です。  
  
## DTN\_FORMATQUERY 通知の処理  
 コントロールが書式指定文字列を解析し、コールバック フィールドがある場合、アプリケーションは **DTN\_FORMAT** と **DTN\_FORMATQUERY** 通知メッセージを送信します。  コールバック フィールドの文字列が通知に含まれています。したがって、コールバック フィールドが呼び出されているかを判断できます。  
  
 **DTN\_FORMATQUERY** 通知が現在のコールバック フィールドに表示される文字列のピクセルの最大許容サイズを取得するために送信されます。  
  
 適切にこの値を計算するには、代わりになるように文字列の高さと幅を、コントロールの表示フォントを使用してフィールドを計算する必要があります。  文字列の実際の計算は [GetTextExtentPoint32](http://msdn.microsoft.com/library/windows/desktop/dd144938) Win32 関数の呼び出しによって簡単に実行されます。  サイズが決定されますが、アプリケーションに返す値を渡し、ハンドラー関数を終了します。  
  
 次の例は、コールバックの文字列のサイズを指定する 1 つです:メソッド  
  
 [!code-cpp[NVC_MFCControlLadenDialog#8](../mfc/codesnippet/CPP/using-callback-fields-in-a-date-and-time-picker-control_1.cpp)]  
  
 一度現在のコールバック フィールドのサイズは、そのフィールドの値を指定する必要があります。計算されます。  これは **DTN\_FORMAT** 通知のハンドラーにされます。  
  
## DTN\_FORMAT 通知の処理  
 アプリケーションで **DTN\_FORMAT** 通知を置き換える文字列を要求するために使用されます。  次の例は、1 種類の可能なメソッドを示しています。:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#9](../mfc/codesnippet/CPP/using-callback-fields-in-a-date-and-time-picker-control_2.cpp)]  
  
> [!NOTE]
>  **NMDATETIMEFORMAT** 構造体へのポインターが適切な型への通知ハンドラーの最初のパラメーターをキャストすることです。  
  
## 参照  
 [CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)   
 [コントロール](../mfc/controls-mfc.md)