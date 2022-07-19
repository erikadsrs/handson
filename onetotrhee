public with sharing class AllHandsOn {
    //HandsOn 1 Lógica
    public static Integer somar(Integer num1, Integer num2) {
        
    return num1+num2;
    }

    public static Integer subtrair(Integer valor1, Integer valor2){

    return valor1-valor2;
    }

    public static Integer multiplicar(Integer value1, Integer value2){

    return value1*value2;
    }

    public static String concatenar(String nossoLema){
        nossoLema = '#Everymind1anos';
    return 'Agora vai'+nossoLema;
    }

    public Integer calcularMedia(Integer med1, Integer med2, Integer med3, Integer med4, Integer med5, Integer media){
        media = (med1 + med2 + med3 + med4 + med5)/5;
    return media;
    }

    public String juntarTextos(String textoA, String textoB){
        textoA = 'Programar' ;
        textoB = 'é incrível';
    return textoA+textoB;
    }

    public static Integer calcularTamanhoTexto(String quantidade){
        quantidade =   'Palavras dificeis';
    return quantidade.length();
    }

    //HandsOn 2 SOQL
    public static List<Contract> retornarContratos (List<Contract> listaContratos){
        List<Contract> todosContratos = [
            SELECT id, ContractNumber
            FROM Contract
        ];
    return todosContratos;
    }
    //atenção ao return type
    public static List<Contract> retornarFinalizados (List<Contract> listaFinalizados){
        List<Contract> finalizedContracts = [
            SELECT id, ContractNumber
            FROM Contract
            WHERE status = 'Finalizado'
        ];
    return finalizedContracts;
    }
    //primeiro return type depois valor recebido
    public static List<Bonus__c> retornarBonusPorId (Id clientId){
        List<Bonus__c> bonusList = [
            SELECT id, name
            FROM Bonus__c
            WHERE id =: clientId
        ];
    return bonusList;
    }

    public static List<Parcela__c> retornarParcelasAltas (List<Parcela__c> listaParcelas){
        List<Parcela__c> parcelasAltas = [
            SELECT id, name, Valor__c
            FROM Parcela__c
            WHERE Valor__c > 10000
        ];
    return parcelasAltas;
    }

    public static Integer retornarAbertos (Integer sizeAbertos){
        List<Contract> contratosAbertos = [
            SELECT id, name, status
            FROM Contract
            WHERE status = 'Em Aberto'
        ];
    return contratosAbertos.size();
    }

    public static List<AggregateResult> somarValorParcelas (Id contractId){
        List<AggregateResult> listaParcelas = [
            SELECT Id, SUM(Valor__c)
            FROM Parcela__c
            WHERE Id =: contractId
            GROUP BY Id
        ];
        return listaParcelas;
    }

    //HandsOn 3 DML
    public static void atualizarOpp (Id newId, Integer newValue){
        Opportunity novaOportunidade = new Opportunity();
        novaOportunidade.Id = newId;
        novaOportunidade.amount = newValue;
        
        update novaOportunidade;
    }

    public static void atualizarStatus(Id clientId){
        Contact client = new Contact();
        client.id = clientId;
        client.Ativo__c = 'false';
        
        update client;
    }

    public static void atualizarStatusParcela(Id parcelaId){
        Parcela__c parcelaNovoStatus = new Parcela__c();
        parcelaNovoStatus.id = parcelaId;
        parcelaNovoStatus.Status = 'Paga';
        update parcelaNovoStatus;
    }

    public static void deletarRegistro(Id idDeletar){
        Parcela__c parcelaExcluir = new Parcela__c();
        parcelaExcluir.id = idDeletar;
        delete parcelaExcluir;
    }

    public static boolean criarContato(Id contatoId, String name, String cargo, Date nascimento, String email){
        if (contatoId |= name |= cargo |= nascimento |= email == null) {
            boolean = false;         
        }else{
            boolean = true;
        }
// RETOMAR DAQUI 
