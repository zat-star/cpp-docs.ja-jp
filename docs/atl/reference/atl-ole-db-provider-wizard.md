---
title: "ATL OLE DB プロバイダー ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.provider.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL OLE DB Provider Wizard
- ATL projects, adding ATL OLE DB providers
ms.assetid: cf91ba78-01d1-4d12-b673-e95d96bfbebe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 660f70be8ec4ac1efcec056c694d0e2fc3256071
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="atl-ole-db-provider-wizard"></a>ATL OLE DB プロバイダー ウィザード
このウィザードでは、OLE DB プロバイダーを構成するクラスを作成します。  
  
## <a name="remarks"></a>コメント  
 Visual Studio 2008 以降では、このウィザードで生成された登録スクリプトは下にある場合は、その COM コンポーネントを登録、 **HKEY_CURRENT_USER**の代わりに**HKEY_LOCAL_MACHINE**です。 この動作を変更するには、設定、**すべてのユーザー コンポーネントを登録**ATL ウィザードのオプションです。  
  
 次の表では、ATL OLE DB プロバイダー ウィザードのオプションについて説明します。  
  
 **短い名前**  
 作成するプロバイダーの短い名前を入力します。 ウィザードで、他の編集ボックスが自動的に設定は、ここの入力に基づきます。 場合は、他のボックスの名前を編集できます。  
  
 **コクラス**  
 コクラスの名前。 ProgID 名は、この名前の一致するように変更されます。  
  
 **属性付き**  
 このオプションは、属性またはテンプレート宣言を使用して、プロバイダー クラスを作成するかどうかを指定します。 このオプションを選択すると、ウィザードは、テンプレートの宣言 (これは、既定のオプション属性付きプロジェクトを作成する場合) の代わりに属性を使用します。 このオプションをオフにすると、ウィザードは、属性 (これは、既定のオプション属性なしのプロジェクトを作成する場合) ではなくテンプレートの宣言を使用します。  
  
 非属性プロジェクトを作成するときにこのオプションを選択する場合、ウィザードは、警告するプロジェクトは属性付きプロジェクトに変換され、続行するかどうするかどうかを確認します。  
  
 **ProgID**  
 ProgID、またはプログラム識別子は、アプリケーションが GUID の代わりに使用できるテキスト文字列です。 ProgID 名の形式*projectname.coclassname です*です。  
  
 **Version**  
 プロバイダーのバージョン番号。 既定値は 1 です。  
  
 **DataSource クラス**  
 データ ソース クラスの名前、C 形式の*Shortname*ソース。  
  
 **データ ソースの .h ファイル**  
 データ ソース クラスのヘッダー ファイル。 このファイルの名前を編集したり、既存のヘッダー ファイルを選択することができます。  
  
 **セッション クラス**  
 C 形式のセッション クラスの名前*Shortname*セッションです。  
  
 **セッションの .h ファイル**  
 セッション クラスのヘッダー ファイルです。 このファイルの名前を編集したり、既存のヘッダー ファイルを選択することができます。  
  
 **コマンド クラス**  
 C 形式のコマンド クラスの名前*Shortname*コマンド。  
  
 **コマンドの .h ファイル**  
 コマンド クラスのヘッダー ファイルです。 この名前は、編集することはできず、行セットのヘッダー ファイルの名前によって異なります。  
  
 **行セット クラス**  
 C 形式の行セット クラスの名前*Shortname*行セット。  
  
 **行セットの .h ファイル**  
 行セット クラスのヘッダー ファイルです。 このファイルの名前を編集したり、既存のヘッダー ファイルを選択することができます。  
  
 **行セットの .cpp ファイル**  
 プロバイダーの実装ファイルです。 このファイルの名前を編集したり、既存の実装ファイルを選択することができます。  
  
## <a name="see-also"></a>参照  
 [ATL OLE DB プロバイダー](../../atl/reference/adding-an-atl-ole-db-provider.md)

