$(document).ready(function () {
        var language = $('#PageContent_LanguageTxt').val();
        var nodeId = $('#PageContent_NodeIdTxt').val();
        var level = $('#PageContent_LevelTxt').val();
        var requestUrl = `/api/NocApi/GetElementsByNodeId?language=${language}&nodeId=${nodeId}`;
        //if (language && nodeId && level)
        //{
            $.ajax({
                method: "GET",
                url: requestUrl,
                dataType: "json",
                data: '{}',
                contentType: "application/json; charset=utf-8",
                dataType: "json",
            })
            .done(function (result) {
                console.log(JSON.stringify(result));                
                const nocList = document.getElementById("NocItemList")

                for (var i = 0; i < result.length; i++) {
                    var tempResult = result[i];
                    const nocTitle = document.createElement("h1");
                    nocTitle.innerText = tempResult.Title;
                    nocList.appendChild(nocTitle);
                    const nocUl = document.createElement("ul");

                    for (var j = 0; j < tempResult.ElementTypeItems.length; j++) {
                        var tempElementTypeItems = tempResult.ElementTypeItems[j];
                        let nocLi = document.createElement("li");
                        nocLi.innerText = tempElementTypeItems.Definition;
                        nocUl.appendChild(nocLi)           
                    }
                    nocList.appendChild(nocUl)
                }

            });
        //}
       
    })
