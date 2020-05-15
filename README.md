```
graph TD;

subgraph salaryModule
    sm["工资统计: id,name,useLineBreak（是否启用换行配置）,useType（是否启用类别配置）,usePMD（是否启用党费）"]
end
subgraph salaryFormula
    sf["工资公式: id,moduleId---fk,expression（公式语句比如f1+m2）,
    startDate,endDate,
    expressionInfo,itemName,lineBreak,type"] 
end

subgraph salarySymbol
    ss["工资项: name,symbol，salaryType（薪资，补贴之类），sheetColName,sheetColNo,colType(导入导出列类型)，showIf "]
end
subgraph salaryItemData
    sd["工资取值: value，symbol,idNumber，salaryYymm(有的有十三薪)，countYymm（正常年月），fileId（工资数据导入时候对应文件id）"]
end
subgraph PMDFormula
    pf["工资公式: id,,expression（公式语句比如f1+m2）,
    startDate,endDate,
    expressionInfo,itemName,lineBreak,type"] 
end
subgraph PMDCoefficient
    pc["党费折算率:startDate,endDate,coefficient"]
end
c[个人工资启用党费]
sm-->sf
sm-->pf
sf-->c
c-->pc
pc-->pf

sf-->ss
pf-->sd
ss-->sd
classDef default fill:#7178,stroke:#3133,stroke-width:4px;


```
