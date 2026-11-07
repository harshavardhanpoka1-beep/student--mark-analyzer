def get_marks(subject):
    while True:
        try:
            marks = float(input("Enter marks for " + subject + ": "))
            if 0 <= marks <= 100:
                return marks
            print("Enter marks between 0 and 100")
        except ValueError:
            print("Enter a valid number")


def calculate_grade(avg):
    if avg >= 90:
        return "A+"
    elif avg >= 80:
        return "A"
    elif avg >= 70:
        return "B"
    elif avg >= 60:
        return "C"
    elif avg >= 50:
        return "D"
    else:
        return "F"


def main():
    print("==============================")
    print("    STUDENT MARKS ANALYZER")
    print("==============================")

    name = input("Enter student name: ")

    subjects = ["Python", "Mathematics", "Physics"]
    marks = {}

    for subject in subjects:
        marks[subject] = get_marks(subject)

    total = sum(marks.values())
    average = total / len(subjects)

    print("\n======= STUDENT REPORT =======")
    print("Name:", name)

    for subject, score in marks.items():
        print(subject, ":", score)

    print("Total:", total, "/ 300")
    print("Average:", average, "%")
    print("Grade:", calculate_grade(average))

    if all(score >= 40 for score in marks.values()):
        print("Result: PASS")
    else:
        print("Result: FAIL")

    print("==============================")


if __name__ == "__main__":
    main()# student--mark-analyzer