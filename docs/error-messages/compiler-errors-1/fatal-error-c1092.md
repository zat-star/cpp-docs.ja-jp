---
title: "致命的なエラー C1092 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1092
dev_langs:
- C++
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 6d93fd662b638126e21d5f5f034138c0e6f0e0ad
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1092"></a>致命的なエラー C1092
エディット コンティニュはデータ型への変更をサポートしません。ビルドが必要です。  
  
 変更または前回成功したビルドからのデータ型を追加します。  
  
-   エディット コンティニュは、クラス、構造体、または列挙型の定義を含む既存のデータ型への変更はできません。 デバッグを停止し、アプリケーションをビルドする必要があります。  
  
-   エディット コンティニュは vc などのプログラム データベース ファイルの場合、新しいデータ型の追加はサポートされません*x*0. pdb (ここで*x* Visual C の使用中のメジャー バージョン) は読み取り専用です。 データ型を追加するには、コンパイラが、書き込みモードで .pdb ファイルを開く必要があります。  
  
### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>現在のデバッグ セッションを終了せずにこのエラーを削除するには  
  
1.  データ型をエラーが起こる前の状態に戻します。  
  
2.  **[デバッグ]** メニューの **[コード変更を適用]**をクリックします。  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>ソース コードを変更せずにこのエラーを削除するには  
  
1.  **[デバッグ]** メニューの **[デバッグの停止]**をクリックします。  
  
2.  **[ビルド]** メニューの **[ビルド]**をクリックします。  
  
 詳細については、次を参照してください。、[サポートされているコード変更](/visualstudio/debugger/supported-code-changes-cpp)します。
