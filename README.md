# Convertor-from-kilometers-to-miles



import tkinter
import tkinter.messagebox

class Convertor:
    def __init__(self):
        self.main_window = tkinter.Tk()
        self.top_frame = tkinter.Frame()
        self.middle_frame = tkinter.Frame()
        self.bottom_frame = tkinter.Frame()

        self.input_lable = tkinter.Label(self.top_frame,text="Enter a distance in kilometers : ")
        self.kilo_entry = tkinter.Entry(self.top_frame,width=10)

        self.input_lable.pack(side="left")
        self.kilo_entry.pack(side="left")

        self.descr = tkinter.Label(self.middle_frame,text="Converted into miles : ",)

        self.value = tkinter.StringVar()

        self.miles_lable = tkinter.Label(self.middle_frame,textvariable=self.value)

        self.descr.pack(side="left")
        self.miles_lable.pack(side="left")

        self.calc_button = tkinter.Button(self.bottom_frame,text="Convert",command=self.convert)
        self.quit_button = tkinter.Button(self.bottom_frame,text="Quit",command=self.main_window.destroy)

        self.calc_button.pack(side="left")
        self.quit_button.pack(side="left")

        self.top_frame.pack()
        self.middle_frame.pack()
        self.bottom_frame.pack()

        tkinter.mainloop()

    def convert(self):
        kilo = float(self.kilo_entry.get())

        miles = kilo*0.6214

        self.value.set(miles)
        
        tkinter.messagebox.showinfo("Response",f"{kilo} Kilometers is equal to {miles} Miles.")

Kilo_cont = Convertor()
