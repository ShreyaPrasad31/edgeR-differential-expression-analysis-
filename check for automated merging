import glob


print """

############################################
#               Data Parser                #
############################################

"""


def gene_ID_ex(in_file_name):

	gene_ID = []
	with open(in_file_name) as infile:
		for line in infile:
			if "gene" not in line:
				gene_ID.append(line.split("\t")[0])

	return set(gene_ID)


def main_pro(file1, file2, out_file_name):

	f = open(out_file_name, 'w')
	#f.write("gene_id"+"	"+"Whatever\n")
	IDs = gene_ID_ex(file1)

	for ID in IDs:
		with open(file2) as infile:
			for t_line in infile:
				if ID.strip("\n") == t_line.split("\t")[0].strip("\t"):
					f.write("	".join([str(ID),str(t_line)]))




if __name__=="__main__":


	infils = glob.glob("*.txt")

	print "List of Availabe files: "
	for x, i in enumerate(infils):
		print x, i
 

	f1 = infils[int(raw_input("Enter Index for Gene_ID File: "))]
	f2 = infils[int(raw_input("Enter Index for Second File: "))] 
	f3 = raw_input("Do you want to Enter Output file name: enter  yes or no, Default is 'output.csv': ").upper()

	

	if f3 == "NO":
		f3 = "output.csv"
	else:
		f3 = raw_input("Enter output file name:" )
	


	print "You have Inpute These two files: ", f1, f2

	try:

		main_pro(f1, f2, f3)
	except:

		print "You have done something terribly Wrong check your input files: "
