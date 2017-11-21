---
title: "新しいカスタム リソースまたはデータ リソースを作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.binary
dev_langs: C++
helpviewer_keywords:
- custom resources [C++]
- data resources [C++]
- resources [Visual Studio], creating
ms.assetid: 9918bf96-38fa-43a1-a384-572f95d84950
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ff1beb01e08ea78f96b7f161e7f3ffc1110ff63b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-new-custom-or-data-resource"></a>新しいカスタム リソースまたはデータ リソースの作成
通常のリソース スクリプト (.rc) ファイル構文を使用してリソースを別個のファイルに置き、それからソリューション エクスプローラーでプロジェクトを右クリックして、ショートカット メニューで **[リソース ファイルのインクルード]** をクリックしてそのファイルをインクルードすることにより、新しいカスタム リソースやデータ リソースを作成することができます。  
  
### <a name="to-create-a-new-custom-or-data-resource"></a>新しいカスタム リソースやデータ リソースを作成するには  
  
1. カスタム リソースやデータ リソースが格納される[.rc ファイルを作成します](../windows/how-to-create-a-resource-script-file.md) 。  
  
     null で終わる引用符で囲まれた文字列として、または 10 進数、16 進数、または 8 進数形式の整数として.rc ファイルにカスタム データを入力することができます。  
  
2.  **ソリューション エクスプローラー**でプロジェクトの .rc ファイルを右クリックし、ショートカット メニューの **[リソース ファイルのインクルード]** をクリックします。  
  
3.  **[コンパイル時に追加するファイル]** ボックスで、カスタム リソースが格納されるファイルの名前を指定する **#include** ステートメントを入力します。 例:  
  
 ```  
    #include mydata.rc  
 ```  
  
     入力する構文とスペルが正しいことを確認します。 **[コンパイル時に追加するファイル]** ボックスの内容が、入力したとおりにリソース スクリプト ファイルに挿入されます。  
  
4.  **[OK]** をクリックして変更を記録します。  
  
 カスタム リソースを作成する別の方法として、外部ファイルをカスタム リソースとしてインポートする方法もあります。 詳細については、「 [リソースのインポートとエクスポート](../windows/how-to-import-and-export-resources.md)」を参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法についてを参照してください[デスクトップ アプリでのリソース](https://msdn.microsoft.com/library/f45fce5x.aspx)で、 *.NET Framework 開発者ガイド 』。* マネージ プロジェクトにリソース ファイルを手動で追加する、リソースにアクセスする、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](https://msdn.microsoft.com/library/xbx3z216.aspx)です。 詳細については、管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションは、次を参照してください。[グローバライズと .NET Framework アプリケーションのローカライズ](https://msdn.microsoft.com/library/h6270d0z.aspx)です。  
  
 要件  
  
 Win32  
  
## <a name="see-also"></a>関連項目  
 [Binary Editor](binary-editor.md)

