---
title: "個々 のコントロールのサイズ変更 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: de656004dc7055af1fec0774248e6b49d664dca3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="sizing-individual-controls"></a>各コントロールのサイズ変更
コントロールのサイズを変更するのにには、サイズ変更ハンドルを使用します。 サイズ変更ハンドルにポインターを配置すると、コントロールをサイズ変更できる方向を示す形状を変更します。 アクティブなサイズ変更ハンドルは、純色です。サイズ変更ハンドルが中空の場合は、その軸に沿ったコントロールのサイズ調整することはできません。  
  
 ガイドや余白の場合に、コントロールのスナップしてコントロールのサイズを変更することもできます。 または移動することによって 1 つは、制御し、ガイド スナップです。  
  
### <a name="to-size-a-control"></a>コントロールのサイズ  
  
1.  コントロールを選択します。  
  
2.  コントロールのサイズを変更するサイズ変更ハンドルをドラッグします。  
  
    -   上と横にあるサイズ変更ハンドルは、水平または垂直方向のサイズを変更します。  
  
    -   コーナーにサイズ変更ハンドルは、水平および垂直方向の両方のサイズを変更します。  
  
    > [!TIP]
    >  SHIFT キーを押しながら右および下方向キーを使用して、一度にコントロールの 1 つのダイアログ単位 (DLU) を変更することです。  
  
### <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>内のテキストに合わせてコントロールのサイズを自動的にする  
  
1.  選択**コンテンツ サイズ**から、**形式**メニュー。  
  
 \- または  
  
-   コントロールを右クリックして選択**コンテンツ サイズ**ショートカット メニューからです。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](https://msdn.microsoft.com/library/f45fce5x.aspx)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](https://msdn.microsoft.com/library/xbx3z216.aspx)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](https://msdn.microsoft.com/library/h6270d0z.aspx)です。  
  
 要件  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)   
 [コントロール](../mfc/controls-mfc.md)

