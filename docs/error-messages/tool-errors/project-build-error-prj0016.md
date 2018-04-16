---
title: プロジェクト ビルド エラー PRJ0016 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- PRJ0016
dev_langs:
- C++
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 056a033ce95926ca8bbf59e6bbc7b11656fcd015
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="project-build-error-prj0016"></a>プロジェクト ビルド エラー PRJ0016
ユーザーのセキュリティ設定は、プロセスが作成されないようにします。 これらの設定は、ビルドで必要です。  
  
 プロセスを使用してプロセスを作成するアクセス許可を持たないユーザーとしてログインしています。 このユーザー アカウントのアクセス許可レベルを変更するか、アカウント管理者に問い合わせてください。  
  
 このエラーは、次のレジストリ キーが設定されている場合にも発生することができます。  
  
 \\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun  
  
 このエラーを解決するには、RestrictRun キーを削除します。 このレジストリ キーが必要な場合は、追加**vcspawn.exe**キーのエントリの一覧にします。  
  
 このエラーのもう 1 つの原因は、ポリシーの設定は含まれていません VCSpawn.exe HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun レジストリ キーの下でこのユーザー アカウントに許可されているウィンドウ プログラムとしてです。  
  
 詳細についてを参照してください。  
  
-   使用できるサポート技術情報記事 324153、 [http://support.microsoft.com/default.aspx?scid=kb;en-us;324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153)です。  
  
-   [システム ポリシーの設定に準拠する](http://msdn.microsoft.com/library/aa372139)、「許可された Windows のアプリケーションのみを実行する」のセクションです。