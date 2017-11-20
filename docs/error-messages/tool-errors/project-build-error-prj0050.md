---
title: "プロジェクト ビルド エラー PRJ0050 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0050
dev_langs: C++
helpviewer_keywords: PRJ0050
ms.assetid: ceef3b37-0acf-4abd-ac62-aa830b4fa145
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a712c370de6f5a3a8cc9d0fd96e7937deddd201e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="project-build-error-prj0050"></a>プロジェクト ビルド エラー PRJ0050
出力を登録できませんでした。 レジストリを変更する適切なアクセス許可があることを確認してください。  
  
 Visual C ビルド システムは、(dll または .exe)、ビルドの出力を登録できませんでした。 レジストリの変更に管理者としてログオンする必要があります。  
  
 .Dll を構築する場合は、regsvr32.exe を使用して手動で .dll を登録しようとすることができます、このビルドが失敗した理由に関する情報を表示する必要があります。  
  
 .Dll を作成していない場合、エラーが発生したコマンドのビルド ログを調べます。