# login_tkinter
protótipo de sistema de login de usuário , usando a biblioteca Tkinter nativa do Python.
#interface_tkinter_dados_usuário#
from tkinter import*

class Application:
    def __init__(self, master=None):
        self.fontePadrao = ("Ariel", '10')
        self.widget1 = Frame(master)
        self.widget1["pady"] = 10
        self.widget1.pack()
        
        
        self.widget2 = Frame(master)
        self.widget2["padx"] = 20
        self.widget2.pack()
        
        self.widget3 = Frame(master)
        self.widget3["padx"] = 20
        self.widget3.pack()

        self.widget4 = Frame(master)
        self.widget4["pady"] = 20
        self.widget4.pack()
        
        self.titulo = Label(self.widget1, text="Dados do usuário")
        self.titulo["font"] = ("Arial", "10", "bold")
        self.titulo.pack()
#widget "Entry": entrada de dados#
        self.nomeLabel = Label(self.widget2,text="Nome", font=self.fontePadrao)
        self.nomeLabel.pack(side=LEFT)
        self.nome = Entry(self.widget2)
        self.nome["width"] = 30
        self.nome["font"] = self.fontePadrao
        self.nome.pack(side=LEFT)

        self.senhaLabel = Label(self.widget3, text="Senha", font=self.fontePadrao)
        self.senhaLabel.pack(side=LEFT)
        self.senha = Entry(self.widget3)
        self.senha["width"] = 30
        self.senha["font"] = self.fontePadrao
        self.senha["show"] = "*"
        self.senha.pack(side=LEFT)

        self.autenticar = Button(self.widget4)
        self.autenticar["text"] = "Autenticar"
        self.autenticar["font"] = ("Calibri", "8")
        self.autenticar["width"] = 12
        self.autenticar["command"] = self.verificaSenha
        self.autenticar.pack()
        
        self.mensagem = Label(self.widget4, text="", font=self.fontePadrao)
        self.mensagem.pack()
#verificar senha
    def verificaSenha(self):
        usuario = self.nome.get()   #get(): recuperar o text digitado pelo usuario#
        senha = self.senha.get()
        if usuario == "usuarioboov" and senha == "boov":
            self.mensagem["text"] = "Autenticado"
        else:
            self.mensagem["text"] = "Erro na autenticação"






root = Tk()
Application(root)
root.mainloop()
