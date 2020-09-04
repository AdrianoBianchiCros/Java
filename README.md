# Java
Lista basica com ArrayList

File Principal.java

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class Principal {
    public static void main(String[] args){
        Menu menu = new Menu();

        System.out.println("Bem vindo ao sistema de To Do List");

        List<String>categorias = new ArrayList();

        boolean continua = true;
        while (continua){
            menu.imprimeMenu();
            String valorDecisao = menu.decisaoUsuario();
        
            switch (valorDecisao){
                case "1":{
                    System.out.println("Digite o nome da categoria sem os pesças");
                    Scanner scanNomeCategoria = new Scanner(System.in);
                    String nomeCategoria = scanNomeCategoria.next();

                    categorias.add(nomeCategoria);
                    break;
                }
                
                case "2":{
                    for(String nome: categorias){
                        System.out.println("Nome da cetegoria :" + nome);
                       
                    }
                    break;
                }

                case "3":{
                    System.out.println("Digite a categoria que seja excluir : ");
                    Scanner scanNomeCategoria = new Scanner(System.in);
                    String NomeCategoria = scanNomeCategoria.next();   
                    if(categorias.contains(NomeCategoria))      {
                        categorias.remove(NomeCategoria);
                     System.out.println("Categoria removida: " + NomeCategoria);
                    }else{
                        System.out.println("Categoria invalida !");
                    }
                    
                    break;                  
                }

                case "0" : {
                    System.exit(0);
                }

                default:{
                    System.out.println("Opçõa invalida !");
                    break;
                }

            }

        }
    
    }
       

}

File Menu.java

import java.util.Scanner;

public class Menu {
    public void imprimeMenu(){
        System.out.println("Digite o numero da categoria que deseja utilizar");

        System.out.println("1)Adicionar categoria ");
        System.out.println("2) Listar todas categorias ");
        System.out.println("3) Excluir categoria ");
        System.out.println("0) Sair do programa");
    }

    public String decisaoUsuario(){
        Scanner decisaoUsuario = new Scanner(System.in);
        String valorDecisao = decisaoUsuario.next();
        return valorDecisao;
    }
}


