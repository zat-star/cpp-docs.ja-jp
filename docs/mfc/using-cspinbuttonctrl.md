---
title: "CSpinButtonCtrl の使い方 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CSpinButtonCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSpinButtonCtrl クラス, 使用"
  - "スピン ボタン コントロール"
  - "アップダウン コントロール"
  - "アップダウン コントロール, スピン ボタン コントロール"
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CSpinButtonCtrl の使い方
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*スピン ボタン コントロール* \(または *アップダウン コントロール*\) は、数値を変更するためにユーザーがクリックする矢印のペアを作成します。  この値は *現在位置*と呼ばれます。  位置は、スピン ボタンの範囲内に保存されます。  ユーザーが上向きの矢印をクリックすると、場所が最大に向かって移動します; そのユーザーが矢印をクリックすると、値が最小に向かって移動します。  
  
 スピン ボタン コントロールを [CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md) クラスで MFC で表されます。  
  
> [!NOTE]
>  既定で、スピン ボタンのゼロに設定される最大 \(0\) と 100 に設定できる最小があります。  最大値が最小値未満であるため、上向きの矢印をクリックすると、位置を減らし、下向きの矢印をクリックすると、そのセルが増加します。  これらの値を変更するために [CSpinButtonCtrl::SetRange](../Topic/CSpinButtonCtrl::SetRange.md) を使用します。  
  
 通常、コンパニオン コントロールの現在の位置が表示されます。  コンパニオン コントロールは *関連ウィンドウ*と呼ばれます。  スピン ボタン コントロールの概要については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の [アップダウン コントロールについて](http://msdn.microsoft.com/library/windows/desktop/bb759889) を参照してください。  
  
 スピン コントロール、およびエディット コントロールの関連ウィンドウは、Visual Studio で作成する場合は、ダイアログ ボックスやウィンドウに最初にエディット コントロールをドラッグし、スピン コントロールをドラッグします。  スピン コントロールを選択し、**\[True\]** に **\[Auto Buddy\]** と **\[Set Buddy Integer\]** のプロパティを設定します。  また **\[配置\]** のプロパティを設定します。; **\[右揃え\]** が最も一般的です。  これらの設定によって、エディット コントロールは、関連するウィンドウとして直接タブ オーダーのエディット コントロールの直前に設定されます。  エディット コントロールは、整数を表示し、スピン コントロールは、エディット コントロールの右側に埋め込まれます。  必要に応じて、[CSpinButtonCtrl::SetRange](../Topic/CSpinButtonCtrl::SetRange.md) のメソッドを使用して、スピン コントロールの有効範囲を設定できます。  イベント ハンドラーは、そのデータ交換を直接スピン コントロールに関連ウィンドウ間で通信する必要はありません。  ウィンドウのシーケンスでページング他の用途にスピン コントロール \(たとえば、またはダイアログ ボックスを使用して、`UDN_DELTAPOS` メッセージのハンドラーを追加し、カスタム動作を設定してから実行します。  
  
## さらに詳しくは次のトピックをクリックしてください  
  
-   [スピン ボタンのスタイル](../mfc/spin-button-styles.md)  
  
-   [スピン ボタンのメンバー関数](../Topic/Spin%20Button%20Member%20Functions.md)  
  
## 参照  
 [コントロール](../mfc/controls-mfc.md)