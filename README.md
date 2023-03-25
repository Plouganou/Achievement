import UIKit

class AboutTableViewController: UITableViewController {

    let sectionTitles = ["App Info", "Developer Info"]
    let appInfoTitles = ["App Name", "Version"]
    let appInfoValues = ["My Awesome App", "1.0"]
    let developerInfoTitles = ["Name", "Email"]
    let developerInfoValues = ["John Doe", "john.doe@example.com"]
    
    override func viewDidLoad() {
        super.viewDidLoad()
        tableView.tableFooterView = UIView()
    }

    // MARK: - Table view data source

    override func numberOfSections(in tableView: UITableView) -> Int {
        return sectionTitles.count
    }

    override func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        if section == 0 {
            return appInfoTitles.count
        } else {
            return developerInfoTitles.count
        }
    }
    
    override func tableView(_ tableView: UITableView, titleForHeaderInSection section: Int) -> String? {
        return sectionTitles[section]
    }

    override func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        let cell = tableView.dequeueReusableCell(withIdentifier: "AboutCell", for: indexPath)
        if indexPath.section == 0 {
            cell.textLabel?.text = appInfoTitles[indexPath.row]
            cell.detailTextLabel?.text = appInfoValues[indexPath.row]
        } else {
            cell.textLabel?.text = developerInfoTitles[indexPath.row]
            cell.detailTextLabel?.text = developerInfoValues[indexPath.row]
        }
        return cell
    }

}
